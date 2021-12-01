<template>
  <div class="dark-theme">
    <v-container fluid>
      <v-row>
        <v-col cols="12">
          <h3 class="pa-3">SUMMARY</h3>
        </v-col>
        <v-col cols="3">
          <InfoField v-for="(item, index) in info" :key="index" :info="item" />
        </v-col>
        <v-divider vertical></v-divider>
        <v-col cols="3">
          <InfoField v-for="(item, index) in info2" :key="index" :info="item" />
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="6">
          <v-btn
            class="font-weight-light text-uppercase mx-2"
            rounded
            color="primary"
            dark
          >
            <span class="px-4"> deferred payment </span>
          </v-btn>
          <v-btn
            class="font-weight-light text-uppercase mx-2"
            rounded
            color="primary"
            plain
          >
            <span class="px-4"> duty suspension </span>
          </v-btn>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12">
          <DataTable />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import InfoField from "./InfoField";
import DataTable from "./DataTable";
export default {
  name: "Summary",
  components: { InfoField, DataTable },
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
    info: [
      {
        title: "Carrier/Operator",
        content: "Lionel Davies",
      },
      {
        title: "Voyage No.",
        content: "4343434343",
      },
      {
        title: "Place Of Destination",
        content: "GHABO - Albo",
      },
      {
        title: "Total Number Of Bills",
        content: "4343543 Lionel Davis",
      },
    ],
    info2: [
      {
        title: "Carrier/Operator",
        content: "Lionel Davies",
      },
      {
        title: "Voyage No.",
        content: "4343434343",
      },
      {
        title: "Place Of Destination",
        content: "GHABO - Albo",
      },
      {
        title: "Status",
        status: "Activate",
      },
    ],
  }),
};
</script>
