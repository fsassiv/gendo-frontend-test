<template>
  <nav class="nav__tabs">
    <button
      id="repos"
      class="nav__tab"
      :class="currentNavTab === 'repos' && 'active'"
      @click="$emit('handleNavClick', $event.target.id)"
    >
      Repos<span class="nav__tab-counter">{{ reposCount }}</span>
    </button>
    <button
      id="starred"
      class="nav__tab"
      :class="currentNavTab === 'starred' && 'active'"
      @click="$emit('handleNavClick', $event.target.id)"
    >
      Starred<span class="nav__tab-counter">{{ starredReposCount }}</span>
    </button>
  </nav>
</template>

<script>
export default {
  name: "NavTabs",
  props: {
    currentNavTab: {
      type: String,
      default: "repos"
    },
    reposCount: {
      type: Number,
      default: 0
    },
    starredReposCount: {
      type: Number,
      default: 0
    }
  },
  emits: ["handleNavClick"]
};
</script>

<style></style>
