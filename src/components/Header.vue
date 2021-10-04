<template>
   <header>
       <div class="logo">
           <img src="../assets/img/spotify-logo.png" alt="">
       </div>

        <Nav @changedGenre='selectedGenre'/>

   </header>
</template>

<script>
import Nav from "./Nav.vue"

export default {
    name: 'Header',
    components: {
        Nav
    },
    data(){
        return{
            choosenGenre: ''
        }
    },
    methods:{

        selectedGenre(selectValue){
            this.choosenGenre = selectValue;
        }
    }
    
}
</script>

<style lang='scss'>
@import "../assets/style/variables.scss";

header{
    max-height: 4.375rem;
    background-color: $header;
    padding: .625rem;
    display: flex;
    align-items: center;
    justify-content: space-between;

    .logo{
        max-width: 3.75rem;

        img{
            width: 100%;
        }
    }
}

</style>