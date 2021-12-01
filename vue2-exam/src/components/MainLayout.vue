<template>
  <div class="mt-15">
    <v-card>
      <div class="main-tabs semi-dark-theme rounded-0">
        <v-tabs
          class="mx-4 rounded-0"
          v-model="tab"
          fixed-tabs
          background-color="#2c2c2c"
          dark
        >
          <v-tab
            class="mx-1 font-weight-light"
            v-for="item in items"
            :key="item.tab"
          >
            {{ item.tab }}
          </v-tab>
        </v-tabs>
      </div>

      <v-tabs-items v-model="tab">
        <v-tab-item v-for="item in items" :key="item.tab">
          <v-card class="dark-theme rounded-0" flat>
            <v-card-text class="dark-theme">
              <Summary />
            </v-card-text>
          </v-card>
        </v-tab-item>
      </v-tabs-items>
    </v-card>
  </div>
</template>

<script>
import Summary from "./Summary.vue";
export default {
  name: "MainLayout",
  components: { Summary },
  data: () => ({
    tab: null,
    items: [
      { tab: "Summary", content: "Tab 1 Content" },
      { tab: "Declaration", content: "Tab 2 Content" },
      { tab: "Guarantee Acc.", content: "Tab 3 Content" },
      { tab: "Shipment", content: "Tab 4 Content" },
      { tab: "Documents", content: "Tab 5 Content" },
      { tab: "Shipping", content: "Tab 6 Content" },
      { tab: "Parties", content: "Tab 7 Content" },
      { tab: "Detail Lines", content: "Tab 8 Content" },
    ],
  }),
};
</script>

<style lang="scss">
.main-tabs {
  .v-tab {
    background: rgb(78, 78, 78);
    border-top-right-radius: 5px;
    border-top-left-radius: 5px;
    border-bottom: none;

    &:hover,
    &:active,
    &:focus {
      background: rgb(29, 29, 29);
    }
  }
  .v-tab--active {
    background: rgb(29, 29, 29);

    &:hover,
    &:active,
    &:focus {
      background: rgb(29, 29, 29);
    }
  }

  .v-slide-group__wrapper {
    background: transparent;
  }

  .v-tabs-slider {
    display: none;
  }
}
</style>
