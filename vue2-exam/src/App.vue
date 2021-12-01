<template>
  <v-app>
    <NavigationBar />
    <v-main class="semi-dark-theme">
      <v-container fluid>
        <MainLayout />
      </v-container>
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

  data: () => ({
    //
  }),
};
</script>
<style>
.dark-theme {
  background-color: #1d1d1d !important;
  color: white !important;
}

.semi-dark-theme {
  background-color: #2c2c2c !important;
  color: white !important;
}
</style>
