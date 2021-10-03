<template>
    
    <div class="canvas">
        <img :src="api.poster" :alt="api.title">
        <div class="info">
            <h2>{{api.title}}</h2>
            <p>{{api.author}}</p>
            <p>{{api.year}}</p>
        </div>
    </div>


  
</template>

<script>
export default {
    name: 'Canvas',
    props:{
        api: Object
    },
}
</script>



<style lang="scss">
@import "../assets/style/variables.scss";

.canvas{
    width: calc(100% / 5 - 2.5rem );
    min-height: 22.5rem;
    margin: .625rem 1.25rem;
    padding: 1.25rem 1.125rem;
    text-align: center;
    background-color: $header;
    overflow: hidden;

    & img{
        width: 100%;
    }

    .info{
        color:$gray;

        h2{
            margin: 1.25rem 0;
            color:$white;
            text-transform: uppercase;
            font-size: 1.25rem;
        }
    }
}

</style>