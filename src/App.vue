<template>
  <div id="app">
    <Header @choosenGenre="passValue" :genresList='genresList' :authorsList='authorsList'/>
    <main>
      <Covers :genre='genre' @genresList='passList' @authorsList='passAuthors' />
    </main>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Covers from "./components/Covers.vue";

export default {
  name: "App",
  components: {
    Header,
    Covers,
  },
  data() {
    return {
      genre: "",
      genresList: [],
      authorsList: []
    };
  },
  methods: {

    passValue(selectValue) {
      this.genre = selectValue;
    },
    passList(list) {
      this.genresList = list;
    },
    passAuthors(list) {
    this.authorsList = list;
    }



  },
};
</script>

<style lang="scss">
@import "./assets/style/common.scss";
</style>
