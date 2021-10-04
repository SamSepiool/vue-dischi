<template>
  <header>
    <div class="logo">
      <img src="../assets/img/spotify-logo.png" alt="" />
    </div>

    <Nav
      @changedGenre="passValue"
      :on="$emit('choosenGenre', choosenGenre)"
      :genresList="genresList"
    />
  </header>
</template>

<script>
import Nav from "./Nav.vue";

export default {
    name: "Header",
    props:{
     genresList: Array,
  },

  components: {
    Nav,
  },
  data() {
    return {
      choosenGenre: "",
    };
  },
  methods: {
    passValue(selectValue) {
      this.choosenGenre = selectValue;
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