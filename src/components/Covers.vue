Skip to content
Search or jump to…
Pull requests
Issues
Marketplace
Explore
 
@SamSepiool 
SamSepiool
/
vue-dischi
Public
1
00
Code
Issues
Pull requests
Actions
Projects
Wiki
Security
Insights
Settings
vue-dischi/src/components/Covers.vue
@SamSepiool
SamSepiool fix Canvas props
Latest commit 85118e7 yesterday
 History
 1 contributor
46 lines (35 sloc)  745 Bytes
   
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
            covers: [],
            genres: [],
            authors: []
        }
    },
       created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( (response) => {
            this.covers = response.data.response;

            this.covers.forEach ((elm) => {
                if ( !this.genres.includes(elm.genre) ) {
                        this.genres.push(elm.genre);
                    } 
                if ( !this.authors.includes(elm.author) ) {
                    this.authors.push(elm.author)
                }
                // (!this.genres.includes(elm.genre)) ?  this.genres.push(elm.genre) : null
                // (!this.authors.includes(elm.author)) ? this.authors.push(elm.author) : null 
            });
            console.log(this.authors)
            console.log(this.genres)
        });
    },
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
