<template>
  <li class="repo">
    <a
      href="#"
      class="repo__title"
      :class="currentNavTab === 'starred' && 'bold'"
      target="_blank"
      >{{ repo.name }}</a
    >
    <p class="repo__description">
      {{ repo.description }}
    </p>
    <div class="repo__icon-bar">
      <span v-if="currentNavTab === 'repos'" class="repo__icon">
        <i class="fas fa-star repo__icon-icon" />
        <span class="repo__icon-text">{{ repo.stargazers_count }} </span>
      </span>
      <span v-if="currentNavTab === 'starred'" class="repo__icon">
        <i class="fas fa-chevron-left repo__icon-icon" />
        <i class="fas fa-chevron-right repo__icon-icon" />
        <span class="repo__icon-text"> {{ repo.language }}</span>
      </span>
      <span class="repo__icon">
        <i class="fas fa-code-branch repo__icon-icon" />
        <span class="repo__icon-text"> {{ repo.forks_count }}</span>
      </span>
    </div>
  </li>
</template>

<script>
export default {
  name: "Repository",
  props: {
    currentNavTab: {
      type: String,
      required: false
    },
    repo: {
      type: Object,
      default: null
    }
  }
};
</script>

<style></style>
