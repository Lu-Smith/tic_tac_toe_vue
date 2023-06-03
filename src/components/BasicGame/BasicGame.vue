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
    handlePlayer(index) {
      if (!this.cells[index]) {
        if (this.player === 'Player 1') {
          this.player = 'Player 2'
          this.move = 'O'
        } else {
          this.player = 'Player 1'
          this.move = 'X'
        }
        this.cells[index] = this.move;
      }
    }
  }
}
</script>

<style>

</style>