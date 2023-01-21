<template>
    <div class="instruct-window">
        <h4 class="title">Instructions</h4>
        <p class="instructions">Only you can save BC's water! Conserve as much water as possible by collecting as many raindrops in your bucket!</p>

        <p class="instructions">Click to switch direction of the bucket! Every 5 droplets you collect will give you a random fun fact!</p>
        <p class="instructions">Be careful not to spill more than 4 droplets, or you'll lose!</p>
        <p class="close" @click="$emit('instruction-toggle')">X</p>
    </div>
</template>

<script>

</script>

<style>
.instruct-window{
    width: 80%;
    height: 80%;
    background-color: green;
    border-radius: 10px;
    display:flex;
    flex-direction: column;
    color:white;
}
.title{
    padding-top: 20px;
    font-size:50px
}
.instructions{
    font-size:25px;
    margin: 10px
}
.close{
    color:white;
    font-size: 30px;
}
</style>