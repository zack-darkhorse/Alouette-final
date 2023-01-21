<template>
  <div id="app">
    <GameWindow/>
  </div>
</template>

<script>

import GameWindow from './components/GameWindow.vue';

export default {
  name: 'App',
  components: {GameWindow
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
  background-size:cover;
  font-family: 'Roboto', sans-serif;
  background-image: url('./assets/background.jpg');

}
</style>
