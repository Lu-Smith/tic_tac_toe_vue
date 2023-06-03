<template>
  <h2>Basic game</h2>
  <h3>{{ player }}</h3>
  <BasicGrid :handlePlayer="handlePlayer" :move="move"/>
</template>

<script>
import BasicGrid from './BasicGrid.vue'

export default {
  components: {
    BasicGrid
  },
  data() {
    return {
      player: 'Player 1',
      move: ''
    };
  },
  methods: {
    handleMove() {
      if (this.player === 'Player 1') {
        this.move = 'X'
      } else {
        this.move = 'O'
      }
      console.log(this.move)
    },
    handlePlayer() {
      if (this.player === 'Player 1') {
        this.player = 'Player 2'
      } else {
        this.player = 'Player 1'
      }
      this.handleMove()
    }
  }
}
</script>

<style>

</style>