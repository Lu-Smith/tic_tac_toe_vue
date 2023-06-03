<template>
  <h2>Basic game</h2>
  <h3>{{ player }}</h3>
  <BasicGrid :handlePlayer="handlePlayer" :move="move" :cells="cells"/>
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
      move: '',
      cells: ['','','','','','','','','']
    };
  },
  methods: {
    handleMove(index) {
      if (this.player === 'Player 1') {
        this.move = 'X'
      } else {
        this.move = 'O'
      }
      if (!this.cells[index]) {
            this.cells[index] = this.move;
          }
      console.log(this.move)
    },
    handlePlayer(index) {
      if (this.player === 'Player 1') {
        this.player = 'Player 2'
      } else {
        this.player = 'Player 1'
      }
      this.handleMove(index)
    }
  }
}
</script>

<style>

</style>