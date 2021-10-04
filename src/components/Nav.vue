<template>
    <nav>
        <select name="genres" v-model="genreSelected" @change="$emit('changedGenre', genreSelected)">
            <option value=""></option>
            <option value="rock">ROCK</option>
            <option value="pop">POP</option>
            <option value="metal">METAL</option>
            <option value="jazz">JAZZ</option>
        </select>  
    </nav>
  
</template>

<script>
export default {
    name: "Nav",
    emits: '',
    data(){
        return{
            genreSelected: ''
        }
    },
}

</script>

<style lang="scss">


</style>