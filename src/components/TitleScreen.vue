
<template>
    <div class='title-screen'>
        <div class='title'>
            Save BC's Water!
        </div>
        <div class='btn-container'>
            <div class="title-btn" @click="titleScreenHandler">Play</div>
            <div class='title-btn' @click="instructionHandler">Instructions</div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'TitleScreen',
    components: {
    },
    methods:{
        titleScreenHandler: function(){
            this.$emit('toggle-screen')
        },
        instructionHandler: function(){
            this.$emit('instruction-toggle')
        }
    }
}
</script>

<style>
.title {
    color: white;
    background-color: green;
    font-size: 50px;
    border-radius: 10px;
    padding: 10px;
}

.title-btn {
    color: white;
    font-size: 50px;
    cursor: pointer;
    border-radius: 10px;
    background-color: green;
    padding: 10px;
}

.title-btn:hover {
    color: red;
}

.btn-container {
    display: flex;
    justify-content: space-around;
    width: 60%;
    padding-top: 150px;
}

.title-screen {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
}
</style>