<template>
    <div class="window" @click="switchDirection">
        <GameHeader :titleToggle="titleToggle" :showFact="showFact" :lives="lives" :score="score"/>
        <TitleScreen @toggle-screen="toggleTitle" @instruction-toggle="toggleInstructions"
            v-if="titleToggle && !instructionShow && !loseToggle" />
        <GameComponents :score='score' :yPositionRain='yPositionRain' :xPosition='xPosition' :titleToggle='titleToggle' :showFact='showFact' :loseToggle='loseToggle' :bucketFill="bucketFill" :xBucket="xBucket"/>
        <FunFact v-if="!titleToggle && showFact" :fact="fact" @close-fact="closeFact"></FunFact>
        <InstructionScreen @instruction-toggle="toggleInstructions" v-if="instructionShow" />
        <LoseScreen :score="score" v-if="loseToggle" @lose-toggle="resetGame"/>

    </div>
</template>

<script>
import TitleScreen from './TitleScreen.vue'
import FunFact from './FunFact.vue'
import InstructionScreen from './InstructionScreen.vue'
import LoseScreen from './LoseScreen.vue'
import GameComponents from './GameComponents.vue'
import GameHeader from './GameHeader.vue'
import commonFacts from './commonFacts.js'
export default {

    data() {
        return {
            yPositionRain: 100,
            xPosition: Math.random(Math.floor(Math.random())) * 60 + 1,
            xBucket: 50,
            bucketDirection: 1,
            bucketFill: 0,
            titleToggle: true,
            instructionShow: false,
            showFact: false,
            score: 0,
            fact: "",
            lives: 5,
            loseToggle: false,
            commonFacts: commonFacts
        }
    },
    name: 'GameWindow',
    components: {
        TitleScreen,
        FunFact,
        InstructionScreen,
        LoseScreen,
        GameComponents,
        GameHeader
    },
    methods: {
        toggleTitle: function () {
            this.titleToggle = false;
        },
        toggleInstructions: function () {
            this.instructionShow = !this.instructionShow
        },
        closeFact: function () {
            this.showFact = false;
        },
        switchDirection: function () {
            this.bucketDirection *= -1
        },
        catchDrop: function () {
            this.score++;
            this.bucketFill += 40;
            if (this.bucketFill == 200) {
                const i = Math.floor(Math.random() * this.commonFacts.length)
                this.fact = this.commonFacts[i];
                this.showFact = true;
                this.bucketFill = 0;
            }
        },
        resetGame: function(){
            this.yPositionRain = 100
            this.xPosition = Math.random(Math.floor(Math.random())) * 60 + 1
            this.xBucket = 50
            this.bucketDirection = 1
            this.bucketFill = 0
            this.titleToggle = true
            this.instructionShow = false
            this.showFact = false
            this.score = 0
            this.fact = ""
            this.lives = 5
            this.loseToggle = false}
        


    },
    mounted: function () {
        window.setInterval(
            () => {
                if (!this.titleToggle && !this.showFact) {
                    this.yPositionRain += 3;
                    this.xBucket += 0.20 * this.bucketDirection
                    if (this.yPositionRain >= 820) {
                        this.yPositionRain = 100
                        this.xPosition = Math.random(Math.floor(Math.random())) * 60 + 1
                        this.lives--
                        if (this.lives == 0) {
                            this.loseToggle = true
                            this.titleToggle = true
                        }

                    }
                    if (this.xBucket < 10 || this.xBucket > 79) {
                        this.bucketDirection *= -1
                    }
                    if (this.yPositionRain >= 730 && this.xBucket - 18 < this.xPosition && this.xBucket - 12 > this.xPosition) {
                        this.yPositionRain = 100
                        this.xPosition = Math.random(Math.floor(Math.random())) * 60 + 1
                        this.catchDrop()
                    }
                }

            }, 10
        )
    }
}
</script>

<style>
.window {
    height: 80%;
    width: 80%;
    background-color: gray;
    border-radius: 10px;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-image: url(../assets/window.webp);
}

</style>