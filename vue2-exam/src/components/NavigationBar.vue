<template>
  <v-app-bar
    absolute
    color="#1e222a"
    elevate-on-scroll
    scroll-target="#scrolling-techniques-7"
  >
    <v-app-bar-nav-icon color="white"></v-app-bar-nav-icon>

    <v-toolbar-title>
      <BreadCrumb />
    </v-toolbar-title>

    <v-spacer></v-spacer>

    <v-btn icon>
      <v-icon size="20" color="#ffffff">mdi-magnify</v-icon>
    </v-btn>

    <v-btn icon class="mr-4 ml-2">
      <v-badge content="14" color="error" top>
        <v-icon size="20" color="#ffffff">mdi-bell</v-icon>
      </v-badge>
    </v-btn>

    <v-btn icon>
      <v-avatar size="30" color="blue">
        <span class="white--text text-h7">CJ</span>
      </v-avatar>
    </v-btn>
  </v-app-bar>
</template>
<script>
import BreadCrumb from "./BreadCrumb";
export default {
  name: "NavigationBar",
  components: { BreadCrumb },
  data: () => ({
    items: [
      {
        text: "Dashboard",
        disabled: false,
        href: "breadcrumbs_dashboard",
      },
      {
        text: "Link 1",
        disabled: false,
        href: "breadcrumbs_link_1",
      },
      {
        text: "Link 2",
        disabled: true,
        href: "breadcrumbs_link_2",
      },
    ],
  }),
};
</script>
