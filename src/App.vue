<template>
  <div class="app">
    <Header />
    <div class="container expanded-mobile expanded-tablet">
      <main class="profile">
        <ProfileInfo />
        <div class="profile__content">
          <NavTabs
            :currentNavTab="currentNavTab"
            @handleNavClick="handleNavClick"
          />
          <Search />
          <keep-alive>
            <component :is="currentTabComponent" />
          </keep-alive>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import Header from "./components/header";
import NavTabs from "./components/nav";
import Repos from "./components/reposTab";
import StarredRepos from "./components/starredReposTab";
import Search from "./components/search";
import ProfileInfo from "./components/profile/Info.vue";

export default {
  name: "App",
  components: {
    Header,
    ProfileInfo,
    NavTabs,
    Repos,
    StarredRepos,
    Search
  },
  data() {
    return {
      currentNavTab: "repos"
    };
  },
  computed: {
    currentTabComponent() {
      if (this.currentNavTab === "starred") {
        return StarredRepos;
      }
      return Repos;
    }
  },
  methods: {
    handleNavClick(eventId) {
      this.currentNavTab = eventId;
    }
  }
};
</script>
