<template>
  <div id="app">
    <Header/>
    <main>
      <Covers/>
    </main>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Covers from "./components/Covers.vue";


export default {
  name: 'App',
  components: {
    Header,
    Covers,

  }
}
</script>

<style lang="scss">
@import "./assets/style/common.scss" ;


</style>
