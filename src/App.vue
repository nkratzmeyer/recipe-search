<template>
  <div id="app">
    <search-page />
    <footer>Created By Nathan Kratzmeyer</footer>
  </div>
</template>

<script>
import SearchPage from "./components/SearchPage.vue";

export default {
  name: "App",
  components: {
    SearchPage,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Playfair+Display:wght@400;700&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: #f9fafb;
}

h1 {
  margin: 15px;
  font-size: 26px;
}

#app {
  display: flex;
  flex-direction: column;
  font-family: Playfair Display;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 1300px;
  margin: 10px auto;
  min-height: 95vh;
}

input[type="text"] {
  height: 30px;
  border: none;
  outline: none;
  padding: 0 10px;
  font-size: 18px;
  margin: 15px;
}

input[type="text"]:focus {
  border: none;
  outline: none;
  background-color: rgb(240, 247, 240);
}

button {
  height: 30px;
  border: none;
  background-color: green;
  color: white;
  padding: 0 9px;
  font-weight: bold;
}

button:focus {
  border: none;
  outline: none;
}

button:hover {
  cursor: pointer;
  background-color: rgb(2, 97, 2);
}

img {
  max-width: 100%;
}

a {
  text-decoration: none;
  color: rgb(32, 114, 32);
}

a:hover {
  font-weight: bold;
}

footer {
  text-align: center;
  font-display: Montserratt;
  flex: 0 0 auto;
  margin-top: 20px;
}

@media only screen and (max-width: 1000px) {
  #app{
    width: 95%;
  }
}
</style>
