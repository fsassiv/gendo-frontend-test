<template>
  <div class="app">
    <Header />
    <div class="container expanded-mobile expanded-tablet">
      <main class="profile">
        <ProfileInfo />
        <div class="profile__content">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Tenetur
          fugit, suscipit debitis minima aut inventore dolor voluptas, corporis
          eius ex quos consequatur necessitatibus at odit nam sed aliquid
          numquam soluta!
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import Header from "./components/header";
import ProfileInfo from "./components/profile/Info.vue";

export default {
  name: "app",
  components: {
    Header,
    ProfileInfo,
  },
};
</script>
