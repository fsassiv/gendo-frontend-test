<template>
  <div class="profile__info container">
    <img
      :src="info && info.avatar_url"
      alt="Prifle image"
      class="profile__info-avatar"
    />
    <div class="profile__info-data">
      <a
        :href="info && info.html_url"
        target="_blank"
        class="profile__info-name bold"
      >
        {{ info && info.login }}
      </a>
      <p class="profile__info-title"></p>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProfileInfo",
  props: {
    info: {
      type: Object,
      required: false,
      default: null
    }
  }
};
</script>
