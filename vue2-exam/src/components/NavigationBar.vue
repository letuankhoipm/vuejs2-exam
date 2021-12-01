<template>
  <v-app-bar
    absolute
    color="#2c2c2c"
    elevate-on-scroll
    scroll-target="#scrolling-techniques-7"
  >
    <v-app-bar-nav-icon color="white"></v-app-bar-nav-icon>

    <v-toolbar-title>
      <BreadCrumb />
    </v-toolbar-title>

    <v-spacer></v-spacer>

    <v-btn icon>
      <v-icon>mdi-magnify</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>mdi-heart</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>mdi-dots-vertical</v-icon>
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
