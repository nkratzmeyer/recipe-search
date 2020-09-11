<template>
  <div class="search-recipe-card">
    <h3 v-html="recipe.title" class="recipe-title"></h3>
    <img class="recipe-img" v-bind:src="image_url" alt srcset />
    <p><span class="bold">Source:</span> {{recipe.publisher}}</p>
    <h5 class="recipe-rank">Rank {{ Math.floor(recipe.social_rank) }}</h5>
    <a class="recipe-source" v-bind:href="recipe.source_url" target="_blank">Recipe Page</a>
  </div>
</template>

<script>
export default {
  props: {
    recipe: {
      type: Object,
      required: true,
    },
  },
  computed : {
    image_url(){
      return this.recipe.image_url.replace('http', 'https');
    }
  }
};
</script>

<style scoped>
.search-recipe-card {
  position: relative;
  font-family: Montserrat;
  display: flex;
  flex-direction: column;
  width: 250px;
  height: 300px;
  padding: 10px;
  /* offset-x | offset-y | blur-radius | spread-radius | color */
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  background-color: white;
}

.search-recipe-card:hover{
      box-shadow: 3px 3px 3px 2px rgba(0, 0, 0, 0.2);
}

.recipe-title {
  font-family: Playfair Display;
  font-size: 18px;
  margin-bottom: 10px;
  text-align: center;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
}

.recipe-img {
  flex: 0 0 150px;
  align-self: center;
  width: 150px;
  height: 150px;
  margin-bottom: 10px;
}

.recipe-source {
  position: absolute;
  bottom: 5px;
  right: 10px;
}

.recipe-rank {
  position: absolute;
  bottom: 5px;
}

.bold{
    font-weight: 500;
}

@media only screen and (max-width: 1000px) {
.search-recipe-card {
  display: flex;
  flex-direction: column;
  width: 95%;
  height: 300px;
  padding: 10px;
}

.recipe-img {
  width: 175px;
  height: 175px;
}
}
</style>