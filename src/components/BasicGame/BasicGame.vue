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
      player: 'player 1'
    };
  },
  methods: {
    handleMove() {
      if (this.player === 'player 1') {
        this.player = 'player 2'
      } else {
        this.player = 'player 1'
      }
    }
  }
}
</script>

<style>

</style>