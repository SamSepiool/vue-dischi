<template>
    <nav>
        <select name="genres" v-model="genreSelected" @change="$emit('changedGenre', genreSelected)">
            <option value="">All genres</option>
            <option v-for="(genre,index) in genresList" :key="index">{{genre}}</option>

        </select>  
    </nav>
  
</template>

<script>
export default {
    name: "Nav",
    props:{
    genresList: Array,
    },
    data(){
        return{
            genreSelected: ''
        }
    },
}

</script>

<style lang="scss">


</style>