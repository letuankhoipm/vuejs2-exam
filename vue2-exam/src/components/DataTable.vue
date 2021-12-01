<template>
  <div>
    <v-row justify="center">
      <v-dialog v-model="dialogVisible" persistent max-width="800px">
        <v-card dark class="px-15 py-6 bg-dialog">
          <v-card-title>
            <span class="text-h6">Example Popup Title</span>
          </v-card-title>

          <div class="popup-tabs px-4 mt-8">
            <v-tabs v-model="tab" background-color="#1e222a" dark>
              <v-tab class="px-4 mr-4" v-for="item in tabItems" :key="item.tab">
                <span class="px-4 font-weight-light">
                  {{ item.tab }}
                </span>
              </v-tab>
            </v-tabs>
          </div>

          <v-tabs-items class="mx-2 bg-dialog" dark v-model="tab">
            <v-tab-item v-for="(item, index) in tabItems" :key="index">
              <v-card-text class="pa-0">
                <v-container>
                  <v-row>
                    <v-col cols="4" sm="6" md="4">
                      <v-text-field label="Name"></v-text-field>
                    </v-col>
                    <v-col cols="4" sm="6" md="4">
                      <v-text-field
                        :rules="rules"
                        label="Tax ID*"
                        required
                        placeholder="000000001"
                      ></v-text-field>
                    </v-col>
                    <v-col cols="6" sm="6" md="4">
                      <v-select
                        label="Domain*"
                        persistent-hint
                        return-object
                        single-line
                      ></v-select>
                    </v-col>
                  </v-row>
                  <v-row>
                    <v-col cols="4" sm="6" md="4">
                      <v-text-field label="Name"></v-text-field>
                    </v-col>
                    <v-col cols="4" sm="6" md="4">
                      <v-text-field
                        :rules="rules"
                        label="Tax ID*"
                        required
                        placeholder="000000001"
                      ></v-text-field>
                    </v-col>
                    <v-col cols="6" sm="6" md="4">
                      <v-select
                        label="Domain*"
                        persistent-hint
                        return-object
                        single-line
                      ></v-select>
                    </v-col>
                  </v-row>
                  <v-row>
                    <v-col cols="4" sm="6" md="4">
                      <v-text-field label="Name"></v-text-field>
                    </v-col>
                    <v-col cols="4" sm="6" md="4">
                      <v-text-field
                        :rules="rules"
                        label="Tax ID*"
                        required
                        placeholder="000000001"
                      ></v-text-field>
                    </v-col>
                    <v-col cols="6" sm="6" md="4">
                      <v-select
                        label="Domain*"
                        persistent-hint
                        return-object
                        single-line
                      ></v-select>
                    </v-col>
                  </v-row>
                </v-container>
              </v-card-text>
              <div class="text-left py-8 px-3">
                <v-spacer></v-spacer>
                <v-btn
                  class="btn-primary mr-2"
                  color="blue darken-1 px-8 font-weight-light"
                  dark
                  @click="closeDialog"
                >
                  Save
                </v-btn>
                <v-btn
                  color="#222732"
                  class="btn-primary font-weight-light"
                  dark
                  @click="closeDialog"
                >
                  Close
                </v-btn>
              </div>
            </v-tab-item>
          </v-tabs-items>
        </v-card>
      </v-dialog>
    </v-row>
    <v-data-table
      dense
      dark
      :headers="headers"
      :items="desserts"
      class="elevation-1 mt-4 dark-theme"
      @click:row="openDialog"
      :footer-props="{
        itemsPerPageText: 'Page size',
      }"
    >
      <template v-slot:[`item.status`]="{ item }">
        <v-chip
          class="my-2 btn-activate"
          v-if="item.status == 'Activated'"
          dark
        >
          <span class="font-weight-regular px-2">
            {{ item.status }}
          </span>
        </v-chip>
        <v-chip class="my-2 btn-disabled" v-if="item.status == 'Disabled'" dark>
          <span class="font-weight-regular px-2">
            {{ item.status }}
          </span>
        </v-chip>
      </template>
      <template v-slot:[`item.actions`]>
        <v-icon small> mdi-dots-horizontal </v-icon>
      </template>
    </v-data-table>
    <div class="my-2">
      <v-pagination
        class="pagination-custom"
        :length="15"
        :total-visible="7"
        dark
      ></v-pagination>
    </div>
  </div>
</template>
<script>
export default {
  data: () => ({
    tab: null,
    desserts: [
      {
        name: "Diamond Logistics",
        taxId: 4400098,
        businessDomain: "Carrier/NVOCC",
        status: "Activated",
      },
      {
        name: "Diamond Logistics",
        taxId: 4400098,
        businessDomain: "Carrier/NVOCC",
        status: "Activated",
      },
      {
        name: "Diamond Logistics",
        taxId: 4400098,
        businessDomain: "Carrier/NVOCC",
        status: "Activated",
      },
      {
        name: "Diamond Logistics",
        taxId: 4400098,
        businessDomain: "Carrier/NVOCC",
        status: "Disabled",
      },
      {
        name: "Diamond Logistics",
        taxId: 4400098,
        businessDomain: "Carrier/NVOCC",
        status: "Activated",
      },
    ],
    headers: [
      { text: "Name", value: "name" },
      { text: "Tax ID", value: "taxId" },
      { text: "Business domain", value: "businessDomain" },
      { text: "Status", value: "status" },
      { text: "", value: "actions" },
    ],
    tabItems: [
      { tab: "Header Tab 1", content: "Tab 1 Content" },
      { tab: "Header Tab 2", content: "Tab 2 Content" },
    ],
    rules: [
      (value) => !!value || "Required.",
      (value) => (value || "").length <= 20 || "Max 20 characters",
      (value) => {
        const pattern =
          /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
        return pattern.test(value) || "Invalid Tax ID.";
      },
    ],
    dialogVisible: false,
  }),
  methods: {
    openDialog() {
      this.dialogVisible = true;
    },
    closeDialog() {
      this.dialogVisible = false;
    },
  },
};
</script>
<style lang="scss">
.popup-tabs {
  .v-tab {
    background-color: #1e222a;
    border-radius: 35px !important;
    height: 35px !important;
    font-size: 12px;
    color: #1976d2 !important;

    &:hover,
    &:active,
    &:focus {
      border-radius: 35px !important;
      background: #1662ad;
      color: white !important;
    }
  }
  .v-tab--active {
    color: white !important;
    background: #1976d2;

    &:hover,
    &:active,
    &:focus {
      border-radius: 35px !important;
      background: #1662ad;
    }
  }

  .v-slide-group__wrapper {
    background: transparent;
  }

  .v-tabs-slider {
    display: none;
  }

  .v-tab:before {
    display: none;
  }
}

.v-data-footer__icons-after,
.v-data-footer__icons-before {
  display: none !important;
}

.pagination-custom {
  position: absolute;
  bottom: 45px;

  .v-pagination__item {
    background: transparent !important;
  }

  .v-pagination__navigation {
    display: none !important;
  }
}
.v-data-footer {
  margin-top: 20px;
  border: none !important;
}

.btn-primary {
  height: 30px !important;
  width: 100px !important;
  font-size: 12px !important;
  border-radius: 8px !important;
}

.bg-dialog {
  background-color: #1e222a !important;
}
</style>
