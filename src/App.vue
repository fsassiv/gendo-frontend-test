<template>
  <div class="app">
    <Header />
    <div class="container expanded-mobile expanded-tablet">
      <main class="profile">
        <ProfileInfo :info="user" />
        <div class="profile__content">
          <NavTabs
            :currentNavTab="currentNavTab"
            @handleNavClick="handleNavClick"
            :reposCount="reposList.length"
            :starredReposCount="starredReposList.length"
          />
          <Search @change="handleChange" />
          <Repos
            :currentNavTab="currentNavTab"
            :list="filteredList.length > 0 ? filteredList : list"
          />
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import Header from "./components/header";
import NavTabs from "./components/nav";
import Repos from "./components/repos";
import Search from "./components/search";
import ProfileInfo from "./components/profile";
import axios from "axios";

export default {
  name: "App",
  components: {
    Header,
    ProfileInfo,
    NavTabs,
    Repos,
    Search
  },
  data() {
    return {
      currentNavTab: "repos",
      user: null,
      reposList: [],
      starredReposList: [],
      filteredList: [],
      searchKeyWord: ""
    };
  },
  computed: {
    list() {
      if (this.currentNavTab === "starred") return this.starredReposList;
      return this.reposList;
    }
  },
  watch: {
    searchKeyWord(value) {
      if (value !== "" || value !== " ") {
        let filteredList = this.list.filter(
          item =>
            (item.name && item.name.toLowerCase().includes(value)) ||
            (item.description && item.description.toLowerCase().includes(value))
        );

        this.filteredList = filteredList;
      } else {
        this.filteredList = [];
      }
    },
    list() {
      this.filteredList = [];
      this.searchKeyWord = "";
    }
  },
  mounted() {
    axios
      .get("https://api.github.com/users")
      .then(({ data }) => {
        this.user = data[this.generateRandonId()];
        this.getrepos(this.user.login);
        this.getStarredRepos(this.user.login);
      })
      .catch(console.error);
  },
  methods: {
    generateRandonId() {
      return Math.floor(Math.random() * 29) + 1;
    },
    handleNavClick(eventId) {
      this.currentNavTab = eventId;
    },
    getrepos(userLogin) {
      axios
        .get(`https://api.github.com/users/${userLogin}/repos`)
        .then(({ data }) => {
          this.reposList = data;
        })
        .catch(error => {
          console.error(error);
          this.reposList = [];
        });
    },
    getStarredRepos(userLogin) {
      axios
        .get(`https://api.github.com/users/${userLogin}/starred`)
        .then(({ data }) => {
          this.starredReposList = data;
        })
        .catch(error => {
          console.error(error);
          this.starredReposList = [];
        });
    },
    handleChange(value) {
      this.searchKeyWord = value;
    }
  }
};
</script>
