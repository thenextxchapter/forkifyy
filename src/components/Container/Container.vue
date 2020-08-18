<template>
  <div class="container">
    <header class="header">
      <img src="../../img/logo.png" alt="Logo" class="header__logo" />
      <Search @list="checkResult" />
      <Likes />
    </header>
    <!-- <div v-if='searchResult' > -->
    <Results 
        @recipe="checkRecipe" 
        @recipeTime="checkTime"
        :recipes="result"  />
    <!-- </div> -->
    <Recipes 
        :recipeResult="recipe"
        :Time="time" 
        />
    <Shopping />
  </div>
</template>

<script>
import Search from "../Search/Search";
import Likes from "../Likes/Likes";
import Results from "../Results/Results";
import Recipes from "../Recipes/Recipes";
import Shopping from "../Shopping/Shopping";

export default {
  name: "Container",
  components: {
    Search,
    Likes,
    Results,
    Recipes,
    Shopping,
  },

  data() {
    return {
      result: [],
      recipe: {},
      time: ''
    };
  },
  //   computed: {
  //     searchResult() {
  //       return this.result;
  //     },
  //   },
  methods: {
    checkResult(val) {
      this.result = val;

    //   console.log(this.searchResult);
    },

    checkRecipe(val) {
        this.recipe = val;
    },

    checkTime(val) {
        this.time = val;
    }
  },
};
</script>

<style src="./Container.css" />
