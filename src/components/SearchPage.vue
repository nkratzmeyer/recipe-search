<template>
  <div class="search-page">
    <h1>Recipe Search</h1>
    <div class="search-area">
      <input v-on:keyup.enter="doSearch" v-model="searchTerm" type="text" placeholder="search by keyword" />
      <button v-on:click="doSearch">SEARCH</button>
    </div>

    <div class="search-results">
      <recipe-card v-for="recipe in recipes" v-bind:key="recipe.id" v-bind:recipe="recipe" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import RecipeCard from "./RecipeCard";

export default {
  name: "SearchPage",
  components: {
    RecipeCard,
  },
  data() {
    return {
      page: 1,
      searchTerm: "",
      recipes: [],
    };
  },
  methods: {
    async doSearch() {
      const searchURL = `https://forkify-api.herokuapp.com/api/search?q=${this.searchTerm}`;
      let response = await axios.get(searchURL);
      if (response) {
        this.recipes = response.data.recipes;
      }

      this.searchTerm = "";
    },
  },
  async created() {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.search-page {
  flex: 1 0 auto;
}

.search-area {
  display: flex;
  background-image: url("../assets/bg1.jpeg");
  height: 70px;
  justify-content: center;
  align-items: center;
  margin-bottom: 15px;
}

.search-results {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  gap: 20px;
  justify-items: center;
}

@media only screen and (max-width: 1000px) {
  body{
    width: 95%;
  }

  .search-results {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}
</style>
