<template>
    <div class="header" v-if="!titleToggle && !showFact">
            <div class="lives" v-if="!titleToggle">
                <img class="heart" src="../assets/heart.png" alt="" v-for="n in lives" :key="Math.random() * n">
            </div>
            <div class="score" v-if="!titleToggle && !showFact"> {{ score }}</div>
        </div>
</template>

<script>
export default {
    props: ['titleToggle','showFact','lives','score']
}
</script>

<style>
.score {
    font-size: 90px;
    font-weight: bold;
    color: white;
    padding:20px;
}

.lives {
    align-items: left;
    display: flex;
    flex-direction: row;
    padding:20px;
}

.heart {
    height: 50px;
    width: 100%;
}

.header {
    height: 80%;
    width: 80%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    position:absolute;
}
</style>