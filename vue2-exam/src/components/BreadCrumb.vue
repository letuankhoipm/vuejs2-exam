<template>
  <div>
    <v-breadcrumbs :items="items">
      <template v-slot:item="{ item }">
        <v-breadcrumbs-item :href="item.href" :disabled="item.disabled">
          <span class="text-white">
            {{ item.text.toUpperCase() }}
          </span>
        </v-breadcrumbs-item>
      </template>
      <template v-slot:divider>
        <v-icon color="white">mdi-chevron-right</v-icon>
      </template>
    </v-breadcrumbs>
  </div>
</template>

<script>
export default {
  name: "BreadCrumb",
  data: () => ({
    items: [
      {
        text: "DECLARATION",
        disabled: false,
        href: "breadcrumbs_dashboard",
      },
      {
        text: "MANIFEST",
        disabled: false,
        href: "breadcrumbs_link_1",
      },
      {
        text: "MANIFEST SUMMARY",
        disabled: true,
        href: "breadcrumbs_link_2",
      },
    ],
  }),
};
</script>
<style>
.text-white {
  color: white !important;
}
</style>
