<template>
  <div>
    <AppHeader :genres-list="genresList" @genre-change="setSelectedGenre" />

    <AppMain :filteredDiscs="filteredDiscs" />
  </div>
</template>

<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      discs: [],
      selectedGenre: "",
      genresList: [],
    };
  },
  computed: {
    filteredDiscs() {
      if (!this.selectedGenre) return this.discs;
      return this.discs.filter((disc) => disc.genre === this.selectedGenre);
    },
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.discs = res.data.response;
        console.log(this.discs);

        this.discs.forEach((disc) => {
          if (!this.genresList.includes(disc.genre)) {
            this.genresList.push(disc.genre);
          }
        });
      });
  },
  methods: {
    setSelectedGenre(genre) {
      this.selectedGenre = genre;
    },
  },
};
</script>

<style lang="scss">
@import "./assets/sass/style.scss";
</style>
