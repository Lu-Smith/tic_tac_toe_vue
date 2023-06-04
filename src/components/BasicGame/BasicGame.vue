<template>
  <h2>Basic game</h2>
  <h3>{{ player }}</h3>
  <BasicGrid :handlePlayer="handlePlayer" :move="move" :cells="cells"/>
  <div v-if="gameOver">
    <h4 >Game Over</h4>
    <h4>{{ player }} won 🥳</h4>
  </div>
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
      cells: ['','','','','','','','',''],
      gameOver: false
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
        console.log(this.cells)   
        if (this.cells[0] === 'O' && this.cells[1] === 'O' && this.cells[2] === 'O' || 
            this.cells[3] === 'O' && this.cells[4] === 'O' && this.cells[5] === 'O' ||
            this.cells[6] === 'O' && this.cells[7] === 'O' && this.cells[8] === 'O' ||
            this.cells[0] === 'O' && this.cells[3] === 'O' && this.cells[6] === 'O' || 
            this.cells[1] === 'O' && this.cells[4] === 'O' && this.cells[7] === 'O' ||
            this.cells[2] === 'O' && this.cells[5] === 'O' && this.cells[8] === 'O' ||
            this.cells[0] === 'O' && this.cells[4] === 'O' && this.cells[8] === 'O' ||
            this.cells[2] === 'O' && this.cells[4] === 'O' && this.cells[6] === 'O' 
        ) {
          this.gameOver = true
          this.player = 'Player 1'
        }   
        if (this.cells[0] === 'X' && this.cells[1] === 'X' && this.cells[2] === 'X' || 
            this.cells[3] === 'X' && this.cells[4] === 'X' && this.cells[5] === 'X' ||
            this.cells[6] === 'X' && this.cells[7] === 'X' && this.cells[8] === 'X' ||
            this.cells[0] === 'X' && this.cells[3] === 'X' && this.cells[6] === 'X' || 
            this.cells[1] === 'X' && this.cells[4] === 'X' && this.cells[7] === 'X' ||
            this.cells[2] === 'X' && this.cells[5] === 'X' && this.cells[8] === 'X' ||
            this.cells[0] === 'X' && this.cells[4] === 'X' && this.cells[8] === 'X' ||
            this.cells[2] === 'X' && this.cells[4] === 'X' && this.cells[6] === 'X' 
        ) {
          this.gameOver = true
          this.player = 'Player 2'
        } 
      }
    }
  }
}
</script>

<style>

</style>