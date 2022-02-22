<template>
  <v-card flat>
     <v-tabs  v-model="currentCategory" align-with-title>
          <v-tabs-slider color="yellow"></v-tabs-slider>

          <v-tab v-for="category in categories" :key="category.name">
            {{ category.name }}
          </v-tab>
        </v-tabs>
      


    <v-tabs-items v-model="currentCategory">
      <v-tab-item v-for="category in categories" :key="category.name">
        <v-container>
          <v-row>
            <v-col v-for="item in category.items" :key="item.name" md="6">
              <v-card >
                <v-img height="200" :src="item.image"></v-img>
                <v-card-title>{{item.name}}</v-card-title>
                <v-card-text><label>{{item.price}}</label></v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-tab-item>
    </v-tabs-items>
  </v-card>
</template>

<script>
import data from "../data/data.js";

export default {
  mounted() {
    this.currentCategory = data.categories.findIndex(
      (c) => c.name == this.$route.params.category
    );
  },
  data: () => ({
    categories: data.categories,
    currentCategory: null,
  }),
};
</script>
