<template>
  <h2>Basic game</h2>
  <h3>{{ player }}</h3>
  <BasicGrid :handleMove="handleMove"/>
</template>

<script>
import BasicGrid from './BasicGrid.vue'

export default {
  components: {
    BasicGrid
  },
  data() {
    return {
      player: 'Player 1'
    };
  },
  methods: {
    handleMove() {
      if (this.player === 'Player 1') {
        this.player = 'Player 2'
      } else {
        this.player = 'Player 1'
      }
    }
  }
}
</script>

<style>

</style>