<template>
  <div class="covers_box">
    <Canvas :api="album" v-for="(album, index) in filteredBy" :key="index" />
  </div>
</template>

<script>
import Canvas from "./Canvas.vue";
import axios from "axios";
export default {
  name: "Covers",
  props: {
    genre: String,
    author: String
  },
  components: {
    Canvas,
  },
  data() {
    return {
      covers: [],
      genres: [],
      authors: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((response) => {
        this.covers = response.data.response;

        this.covers.forEach((elm) => {
          if (!this.genres.includes(elm.genre)) {
            this.genres.push(elm.genre);
          }
          if (!this.authors.includes(elm.author)) {
            this.authors.push(elm.author);
          }
        });
        this.genres.push("");
        this.authors.push("");
        this.$emit("genresList", this.genres);
        this.$emit("authorsList", this.authors);
      });
  },

  computed: {
    filteredBy() {
      const coversFiltered = this.covers.filter((elm) => {


        elm.genre = elm.genre.toLowerCase();
        elm.author = elm.author.toLowerCase();

        if(elm.genre.includes(this.genre.toLowerCase()) || this.genre.toLowerCase() == 'all genres'){
          return true;

        }
       
        return false
      });
      return coversFiltered;
    },
  },
};
</script>



<style lang='scss'>
@import "../assets/style/variables.scss";
.covers_box {
  max-width: 71.875rem;
  margin: auto;
  display: flex;
  flex-wrap: wrap;
}
</style>
