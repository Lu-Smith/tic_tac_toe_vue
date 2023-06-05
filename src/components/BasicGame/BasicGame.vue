<template>
  <h2>{{ title }}</h2>
  <transition-group name="playGame" tag="div" class="play-game">
    <template v-if="!gameOver">
    <h3 >{{ player }}</h3>
  </template>
  <template v-else>
      <h3>{{ winner }}</h3>
      <br />
      <button @click="playAgain" class="play-again">Play again</button>
  </template>
  </transition-group>
  <BasicGrid :handlePlayer="handlePlayer" :move="move" :cells="cells" :gameOver="gameOver"/>
  <h4 v-if="gameOver">Game Over</h4>
</template>

<script lang="ts">
import BasicGrid from './BasicGrid.vue'

export default {
  components: {
    BasicGrid
  },
  data() {
    return {
      title: 'Start Playing',
      player: 'Player 1',
      move: '',
      cells: ['','','','','','','','',''],
      gameOver: false,
      winner: ''
    };
  },
  methods: {
    playAgain() {
      this.cells = ['','','','','','','','','']
      this.gameOver = false 
      this.title = 'Start Playing'     
      if (this.winner === 'Player 1 won!') {
            this.player = 'Player 2'
            this.winner = ''
      } else if (this.winner === 'Player 2 won!') {
            this.player = 'Player 1'
            this.winner = ''
      } else if (this.winner === 'Draw') {
            this.player = 'Player 1'
            this.winner = ''
      }
    },
    handlePlayer(index: number) {
        this.title = 'Basic Game' 
        if (!this.cells[index]) {
          if (this.player === 'Player 1') {
            this.player = 'Player 2'
            this.move = 'O'
          } else if (this.player === 'Player 2') {
            this.player = 'Player 1'
            this.move = 'X'
          }
          this.cells[index] = this.move; 
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
            this.winner = 'Player 1 won!'
            this.move = ''
            this.player = ''
          } else if (this.cells[0] === 'X' && this.cells[1] === 'X' && this.cells[2] === 'X' || 
              this.cells[3] === 'X' && this.cells[4] === 'X' && this.cells[5] === 'X' ||
              this.cells[6] === 'X' && this.cells[7] === 'X' && this.cells[8] === 'X' ||
              this.cells[0] === 'X' && this.cells[3] === 'X' && this.cells[6] === 'X' || 
              this.cells[1] === 'X' && this.cells[4] === 'X' && this.cells[7] === 'X' ||
              this.cells[2] === 'X' && this.cells[5] === 'X' && this.cells[8] === 'X' ||
              this.cells[0] === 'X' && this.cells[4] === 'X' && this.cells[8] === 'X' ||
              this.cells[2] === 'X' && this.cells[4] === 'X' && this.cells[6] === 'X' 
          ) {
            this.gameOver = true
            this.winner = 'Player 2 won!'
            this.move = ''
            this.player = ''
        } else if (this.cells.every(cell => cell !== '')) {
            this.gameOver = true
            this.winner = 'Draw'
            this.move = ''
            this.player = ''
        }
      }
    }
  }
}
</script>

<style>
  .playGame-enter-active,
  .playGame-leave-active {
    transition: transform 0.5s;
  }

  .playGame-enter,  
  .playGame-leave-to {
    transform: scale(0);
  }

  .play-again {
    width: 200px;
    background: rgb(173, 83, 137);
    font-size: 20px;
  }

  .play-game {
    height: 160px;
  }

  @media screen and (max-width: 480px) {
    .play-again {
      width: 150px;
      font-size: 16px;
    }
  }

</style>