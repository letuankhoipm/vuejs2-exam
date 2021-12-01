<template>
  <v-app>
    <NavigationBar />
    <v-main class="semi-dark-theme">
      <MainLayout />
    </v-main>
  </v-app>
</template>

<script>
import NavigationBar from "./components/NavigationBar";
import MainLayout from "./components/MainLayout";

export default {
  name: "App",

  components: {
    NavigationBar,
    MainLayout,
  },

  data: () => ({}),
};
</script>
<style lang="scss">
@import "./assets/main.scss";
</style>
