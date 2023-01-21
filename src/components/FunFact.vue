<template>
    <div class="container">
        <p class="fact">{{ fact }}</p>
        <div class="close" @click="$emit('close-fact')">X</div>
    </div>

</template>

<script>
export default {
    name: 'TitleScreen',
    components: {
    },
    methods: {
    },
    props: ['fact']
}
</script>

<style>
.container {
    border-radius: 30px;
    padding-top: 50px;
    padding-bottom: 50px;
    height: 360px;
    width: 563px;
    background-repeat: no-repeat;
    display: flex;
    flex-direction: column;
    align-items: center;
    top: 25%;
    left: 25%;
    z-index: 100;
    background-image: url("../assets/funfact.jpg");
}

.title {
    margin-top: 0px;
    font-size: 40px;
    font-weight: bold;
}

.fact {
    padding-left: 50px;
    padding-right: 50px;
    padding-top: 70px;
    padding-bottom: 40px;
    font-size: 20px;
    color: white;
    
}
.close{
    color:white;
    font-size: 30px;
}
.close:hover{
    cursor:pointer
}
</style>