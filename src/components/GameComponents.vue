<template>
    <div>
        <div class='raindrop' :style="{ top: `${yPositionRain}px`, left: `${20 + xPosition}%` }"
            v-if="!titleToggle && !showFact"></div>
        <div class="bucket" v-if="!titleToggle" :style="{ left: `${xBucket}%` }"></div>
        <div class="meter" v-if="!showFact && !loseToggle" :style="{ height: `${bucketFill}px`, left: `${xBucket}%` }"></div>
    </div>
</template>

<script>
export default {
    props: ['score','yPositionRain','xPosition','titleToggle','showFact','loseToggle','bucketFill','xBucket']
}
</script>

<style>
.raindrop {
    background-color: blue;
    width: 20px;
    height: 20px;
    border-radius: 0 50% 50% 50%;
    border: 3px solid black;
    transform: rotate(45deg);
    margin-top: 20px;
    position: absolute;
}

.ocean {
    background-color: blue;
}

.bucket {
    height: 200px;
    width: 200px;
    position: absolute;
    top: 750px;
    background-image: url('../assets/bucket.png');
    background-size: contain;
    background-repeat: no-repeat;
}

.meter {
    width: 20px;
    background-color: blue;
    position: absolute;
    top: 675px
}
</style>