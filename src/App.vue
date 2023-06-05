<template>
  <MainHeader :handleSwitchGame="handleSwitchGame"/>
  <h1>Tic Tac Toe</h1>
  <BasicGame v-if="gameLevel"/>
  <AdvancedGame v-if="!gameLevel" />
  <MainFooter />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import AdvancedGame from './components/AdvancedGame/AdvancedGame.vue';
import BasicGame from './components/BasicGame/BasicGame.vue';
import MainFooter from './components/Footer/MainFooter.vue';
import MainHeader from './components/MainHeader.vue';

export default defineComponent({
  name: 'App',
  components: {
    MainFooter,
    MainHeader,
    BasicGame,
    AdvancedGame,
  },
  data() {
    return {
      gameLevel: true
    }
  },
  methods: {
    handleSwitchGame() {
      this.gameLevel = !this.gameLevel
    }
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 30px;
  background: radial-gradient(circle at 18.7% 37.8%, rgb(250, 250, 250) 0%, rgb(225, 234, 238) 90%);
  color: rgb(32, 38, 57);
  padding: 30px;
  border-radius: 30px;
  height: 85vh;
}
</style>
