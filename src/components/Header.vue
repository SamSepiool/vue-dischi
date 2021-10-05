<template>
  <header>
    <div class="logo">
      <img src="../assets/img/spotify-logo.png" alt="" />
    </div>

    <Nav
      @changedGenre="passValue"
      @changedAuthor='passValue'
      :genresList="genresList"
      :authorsList="authorsList"
    />
  </header>
</template>

<script>
import Nav from "./Nav.vue";

export default {
    name: "Header",
    props:{
     genresList: Array,
     authorsList: Array
  },

  components: {
    Nav,
  },
  data() {
    return {
      choosenGenre: '',
      choosenAuthor: ''
    };
  },
  methods: {
    passValue(selectValue) {
      if (this.genresList.includes(selectValue)) {
        this.choosenGenre = selectValue;
        this.$emit('choosenGenre', this.choosenGenre)
      }
      if (this.authorsList.includes(selectValue)) {
        this.choosenAuthor = selectValue;
        this.$emit('choosenAuthor', this.choosenAuthor)
      }
    },
    
  },
};
</script>

<style lang='scss'>
@import "../assets/style/variables.scss";

header {
  max-height: 4.375rem;
  background-color: $header;
  padding: 0.625rem;
  display: flex;
  align-items: center;
  justify-content: space-between;

  .logo {
    max-width: 3.75rem;

    img {
      width: 100%;
    }
  }
}
</style>