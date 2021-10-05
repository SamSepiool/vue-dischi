<template>
    <nav>
        <select name="genres" v-model="genreSelected" @change="$emit('changedGenre', genreSelected)">
            <option value="">All genres</option>
            <option v-for="(genre,index) in genresList" :key="index">{{genre}}</option>
        </select>  

        <select name="authors" v-model="authorSelected" @change="$emit('changedAuthor', authorSelected)">
            <option value="">All authors</option>
            <option v-for="(author,index) in authorsList" :key="index">{{author}}</option>
        </select>  
    </nav>
  
</template>

<script>
export default {
    name: "Nav",
    props:{
    genresList: Array,
    authorsList: Array
    },
    data(){
        return{
            genreSelected: '',
            authorSelected: ''
        }
    },
}

</script>

<style lang="scss">


</style>