<template>
  <div id="app">
    <Header @choosenGenre="passValue" :genresList='genresList'/>
    <main>
      <Covers :genre='genre' @genresList='passList' />
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
    };
  },
  methods: {

    passValue(selectValue) {
      this.genre = selectValue;
    },
    passList(list) {
      this.genresList = list;
    }



  },
};
</script>

<style lang="scss">
@import "./assets/style/common.scss";
</style>
