<template>
  <h2>Advanced game</h2>
  <h3 v-if="!gameOver">{{ player }}</h3>
  <div v-else>
    <h3>{{ winner }} won!</h3>
    <br />
    <button @click="playAgain" class="play-again">Play again</button>
  </div>
  <AdvancedGrid :handlePlayer="handlePlayer" :move="move" :cells="cells"/>
  <h4 v-if="gameOver">Game Over</h4>
</template>

<script lang="ts">
import AdvancedGrid from './AdvancedGrid.vue'

export default {
  components: {
    AdvancedGrid
  },
  data() {
    return {
      player: 'Player 1',
      move: '',
      cells: ['','','','','','','','','','','','','','','',''],
      gameOver: false,
      winner: ''
    };
  },
  methods: {
    playAgain() {
      this.cells = ['','','','','','','','','','','','','','','','']
      this.gameOver = false      
      if (this.winner === 'Player 1') {
            this.player = 'Player 2'
            this.winner = ''
      } else if (this.winner === 'Player 2') {
            this.player = 'Player 1'
            this.winner = ''
          }
    },
    handlePlayer(index) {
        if (!this.cells[index]) {
          if (this.player === 'Player 1') {
            this.player = 'Player 2'
            this.move = 'O'
          
          } else if (this.player === 'Player 2') {
            this.player = 'Player 1'
            this.move = 'X'
          }
          this.cells[index] = this.move; 
          if (this.cells[0] === 'O' && this.cells[1] === 'O' && this.cells[2] === 'O' && this.cells[3] === 'O'|| 
              this.cells[4] === 'O' && this.cells[5] === 'O' && this.cells[6] === 'O' && this.cells[7] === 'O'||
              this.cells[8] === 'O' && this.cells[9] === 'O' && this.cells[10] === 'O' && this.cells[11] === 'O'||
              this.cells[12] === 'O' && this.cells[13] === 'O' && this.cells[14] === 'O' && this.cells[15] === 'O'|| 
              this.cells[0] === 'O' && this.cells[4] === 'O' && this.cells[8] === 'O' && this.cells[12] === 'O'||
              this.cells[1] === 'O' && this.cells[5] === 'O' && this.cells[9] === 'O' && this.cells[13] === 'O'||
              this.cells[2] === 'O' && this.cells[6] === 'O' && this.cells[10] === 'O' && this.cells[14] === 'O'||
              this.cells[3] === 'O' && this.cells[7] === 'O' && this.cells[11] === 'O' && this.cells[15] === 'O' ||
              this.cells[0] === 'O' && this.cells[5] === 'O' && this.cells[10] === 'O' && this.cells[15] === 'O' ||
              this.cells[3] === 'O' && this.cells[6] === 'O' && this.cells[9] === 'O' && this.cells[12] === 'O' 
          ) {
            this.gameOver = true
            this.winner = 'Player 1'
            this.move = ''
            this.player = ''
          } else if (this.cells[0] === 'X' && this.cells[1] === 'X' && this.cells[2] === 'X' && this.cells[3] === 'X'|| 
              this.cells[4] === 'X' && this.cells[5] === 'X' && this.cells[6] === 'X' && this.cells[7] === 'X'||
              this.cells[8] === 'X' && this.cells[9] === 'X' && this.cells[10] === 'X' && this.cells[11] === 'X'||
              this.cells[12] === 'X' && this.cells[13] === 'X' && this.cells[14] === 'X' && this.cells[15] === 'X'|| 
              this.cells[0] === 'X' && this.cells[4] === 'X' && this.cells[8] === 'X' && this.cells[12] === 'X'||
              this.cells[1] === 'X' && this.cells[5] === 'X' && this.cells[9] === 'X' && this.cells[13] === 'X'||
              this.cells[2] === 'X' && this.cells[6] === 'X' && this.cells[10] === 'X' && this.cells[14] === 'X'||
              this.cells[3] === 'X' && this.cells[7] === 'X' && this.cells[11] === 'X' && this.cells[15] === 'X' ||
              this.cells[0] === 'X' && this.cells[5] === 'X' && this.cells[10] === 'X' && this.cells[15] === 'X' ||
              this.cells[3] === 'X' && this.cells[6] === 'X' && this.cells[9] === 'X' && this.cells[12] === 'X' 
          ) {
            this.gameOver = true
            this.winner = 'Player 2'
            this.move = ''
            this.player = ''
        } 
      }
    }
  }
}
</script>

<style>

</style>