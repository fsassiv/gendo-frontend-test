<template>
  <ul>
    <Repository
      v-for="repo in list"
      :key="repo.id"
      :currentNavTab="currentNavTab"
      :repo="repo"
    />
  </ul>
</template>

<script>
import Repository from "../repo";

export default {
  name: "Repos",
  components: {
    Repository
  },
  props: {
    currentNavTab: {
      type: String,
      required: false
    },
    reposList: {
      type: Array,
      required: false,
      default: () => []
    },
    list: {
      type: Array,
      required: false,
      default: () => []
    }
  }
};
</script>

<style></style>
