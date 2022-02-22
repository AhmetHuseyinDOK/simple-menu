<template>
  <v-card flat>
    <v-tabs v-model="currentCategory" align-with-title>
      <v-tabs-slider></v-tabs-slider>

      <v-tab v-for="category in categories" :key="category.name">
        {{ category.name }}
      </v-tab>
    </v-tabs>

    <v-tabs-items v-model="currentCategory">
      <v-tab-item v-for="category in categories" :key="category.name">
        <v-container>
          <v-row>
            <v-col
              v-for="(item, index) in category.items"
              :key="item.name"
              md="3"
              cols="6"
            >
              <v-slide-y-transition>
                <v-card height="250" v-show="showCards >= index">
                  <v-img height="150" :src="item.image"></v-img>
                  <v-card-title>{{ item.name }}</v-card-title>
                  <v-card-text
                    ><label>{{ item.price }}</label></v-card-text
                  >
                </v-card>
              </v-slide-y-transition>
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
    this.showCards = 0;
    data.categories[this.currentCategory].items.forEach((item, index) => {
      setTimeout(() => {
        this.showCards = index;
      }, index * 150);
    });

    this.currentCategory = data.categories.findIndex(
      (c) => c.name == this.$route.params.category
    );
  },
  data: () => ({
    showCards: 0,
    categories: data.categories,
    currentCategory: null,
  }),
};
</script>

<style>
</style>