<template>
 
    <div class="covers_box">
        <Canvas :api="album" v-for="(album, index) in covers" :key="index"/>
    </div>
     
</template>

<script>
import Canvas from "./Canvas.vue";
import axios from "axios";

export default {

    name: 'Covers',
    components:{
        Canvas
    },
    data(){
        return{
            covers: []
        }
    },

    created(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) =>{
            this.covers = response.data.response;
        });   
    }
}
</script>



<style lang='scss'>
@import "../assets/style/variables.scss";

.covers_box{
    max-width: 71.875rem;
    margin: auto;
    display: flex;
    flex-wrap: wrap;
}

</style>