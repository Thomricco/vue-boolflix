<template>
  <div id="app">
    <search-bar @search="filterResult" />
    <main-container :films="filmsFiltered" />
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
      filmsFiltered: [],
    };
  },
  mounted() {
    axios
      .get(
        "https://api.themoviedb.org/3/search/movie?query=ritorno+al+futuro&api_key=e99307154c6dfb0b4750f6603256716d"
      )
      .then((response) => {
        console.log(response);
        this.films = response.data.results;
        this.filmsFiltered = response.data.results;
      });
  },
  methods: {
    filterResult(keyword) {

      /*this.filmsFiltered = [];
      for (let index = 0; index < this.films.length; index++) {
        const film = this.films[index];
        if (film.title.toLowerCase().includes(keyword.toLowerCase())) {
          this.filmsFiltered.push(film);
        }
      }*/
  
      this.filmsFiltered = this.films.filter((film) => {
        return film.title.toLowerCase().includes(keyword.toLowerCase());
      });
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");
@import "./style/main.scss";
</style>
