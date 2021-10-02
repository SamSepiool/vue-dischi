<template>
   <header>
       <div class="logo">
           <img src="../assets/img/spotify-logo.png" alt="">
       </div>
   </header>
</template>

<script>
export default {
    name: 'Header',

}
</script>

<style lang='scss'>
@import "../assets/style/variables.scss";

header{
    height: 4.375rem;
    background-color: $header;
    padding: .625rem;

    .logo{
        max-width: 3.75rem;

        img{
            width: 100%;
        }
    }

}



</style>