<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex justify-center" style="width: 100%">
        <v-btn
          text
          style="position: absolute; left: 10px"
          v-show="showBackButton"
          to="/"
          ><v-icon>mdi-arrow-left</v-icon></v-btn
        >

        <v-toolbar-title style="font-family: 'Dancing Script', cursive; !important">
          {{ name }}</v-toolbar-title
        >
      </div>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
import data from "./data/data.js";
export default {
  name: "App",
  computed: {
    showBackButton() {
      return this.$route.params?.category != null;
    },
  },
  data: () => ({
    name: data.companyName,
  }),
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap');
</style>