<template>
  <v-container class="info-field" fluid>
    <v-row>
      <v-col class="py-0 label align-self-center" cols="6">
        {{ info.title }}
      </v-col>
      <v-col class="py-0" cols="6">
        {{ info.content }}

        <v-btn
          v-if="info.status"
          class="text-capitalize font-weight-light"
          rounded
          color="success"
          dark
        >
          Activated
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "InfoField",
  props: ["info"],
  data: () => ({}),
};
</script>
<style lang="scss">
.info-field {
  .label {
    width: 200px;
  }
}
</style>
