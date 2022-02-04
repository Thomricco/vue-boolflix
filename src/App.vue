<template>
  <div id="app">
    <search-bar @search="searchMovies" />
    <main-container :films="films" :series="series"/>
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar.vue";
import MainContainer from "./components/MainContainer.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    SearchBar,
    MainContainer,
  },
  data() {
    return {
      films: [],
      series: [],
    };
  },

  mounted() {
    axios.get("https://api.themoviedb.org/3/movie/popular?&api_key=e99307154c6dfb0b4750f6603256716d").then((response) => {
        console.log(response);
        this.films = response.data.results;
      });
      axios.get("https://api.themoviedb.org/3/tv/popular?&api_key=e99307154c6dfb0b4750f6603256716d").then((res) => {
        
        this.series = res.data.results;
      });
  },
  methods: {
    searchMovies(query) {
      axios.get(`https://api.themoviedb.org/3/search/movie?query=${query}&api_key=e99307154c6dfb0b4750f6603256716d`).then((res) => {
        this.films = res.data.results;

      })
  }

  },
  searchSeries(query) {
      axios.get(`https://api.themoviedb.org/3/search/tv?query=${query}&api_key=e99307154c6dfb0b4750f6603256716d`).then((res) => {
        this.series = res.data.results;

      })
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");
@import "./style/main.scss";
</style>




