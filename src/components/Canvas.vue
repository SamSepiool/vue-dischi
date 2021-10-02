<template>
    
    <div class="canvas">
        <img src="../assets/img/spotify-logo.png" alt="">
        
        <div class="info">
            <h2>SONG</h2>
            <p>ARTIST</p>
            <p>YEAR</p>
        </div>
    </div>


  
</template>

<script>
export default {
    name: 'Canvas',

}
</script>


<style lang="scss">
@import "../assets/style/variables.scss";

.canvas{
    width: calc(100% / 5 - 1.25rem);
    margin: .3125rem .625rem;
    min-height: 18.75rem;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    text-align: center;
    background-color: $header;
    overflow: hidden;

    & img{
        width: 100%;
        max-width: 9.375rem;
        
    }

    .info{
        h2{
            margin-bottom: 1.25rem;
            color:$white;
        }
        p{
            color: gray;
        }
    }
}

</style>