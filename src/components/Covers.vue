<template>
    <div class="wrapper">  
        <div class="covers_box">
            <Canvas/>
            <Canvas/>
            <Canvas/>
            <Canvas/>
            <Canvas/>
            <Canvas/>
            <Canvas/>
            <Canvas/>
            <Canvas/>
            <Canvas/>
        </div>
    </div>   
</template>

<script>
import Canvas from "./Canvas.vue";

export default {

    name: 'Covers',
    components:{
        Canvas
    },
  

}
</script>



<style lang='scss'>
@import "../assets/style/variables.scss";



.wrapper{
    display: flex;
    align-content: center;
    height: 100%;

    .covers_box{
        width: 70%;
        margin: auto;
        display: flex;
        flex-wrap: wrap;
}
}
    
    
    











</style>