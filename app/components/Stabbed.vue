
<template>
  <div class="stabbed">
      <div class="btnRestartContainer">
        <div class="restart" v-on:click="switchToChar()" ></div>
      </div>
  </div>
</template>

<style>
    .stabbed {
    min-width: 100vw;
    min-height: 100vh;
    background-image: url('../assets/guet-apens.jpg');
    background-size: cover;
    }

    .restart {
    position: absolute;
  bottom: 2%;
  right: 5%;
  width: 176px;
  height: 74px;
  background-image: url('../assets/replay.svg');
  background-size: contain center no-repeat;
  background-repeat: no-repeat;
  z-index: 1;
  cursor:pointer;
    }
</style>

<script>
import gameService from '../services/gameService';
import game from '../data.json';
export default {
  data() {
    return {
      show: true,
      gameService: gameService,
      message: 'GAME OVER',
      endMessage: gameService.endContent
    }
  },
  methods: {
    switchToChar() {
      this.$router.push({path: '/characters'})
    }
  }
};
console.log(gameService.endContent);
</script>