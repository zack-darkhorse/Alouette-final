<template>
    <div class="lose-window">
        <h4 class="title">You spilled too much water!</h4>
        <p class="instructions">You'll get them all next time!</p>
        <p class="instructions">Your score: {{ score }}</p>
        <p class="close" @click="$emit('lose-toggle')">Play Again</p>
    </div>
</template>

<script>
export default {
    name: 'LoseScreen',
    components: {
    },
    methods: {
    },
    props: ['score']
}
</script>

<style>
.lose-window{
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
    font-size:40px;
    margin: 10px
}
.close{
    color:white;
    font-size: 30px;
}
</style>