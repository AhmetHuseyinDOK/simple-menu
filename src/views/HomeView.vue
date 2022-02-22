<template>
  <div class="home">
    <v-container>
      <v-row>
        <v-col v-for="category in categories" :key="category.name" md="6">
          <v-card :to="`/${category.name}`">
            <v-img height="200" :src="category.image"></v-img>
            <v-card-title>{{ category.name }}</v-card-title>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src
import data from "../data/data.js";

export default {
  name: "HomeView",
  components: {},
  data: () => ({
    categories: data.categories,
  }),
};
</script>
