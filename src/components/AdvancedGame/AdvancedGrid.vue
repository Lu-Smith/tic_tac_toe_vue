<template>
  <transition-group class="grid" name="grid" tag="div">
    <div 
      class="cell" 
      v-for="(cell, index) in cells" :key="index" 
      @click="handlePlayer(index)"
      :style="{color: gameOver ? 'white' : 'black', background: gameOver ? 'grey' : 'linear-gradient(109.5deg, rgb(13, 101, 136) 9.4%, rgb(86, 201, 255) 78.4%)' }">
    {{ cell }}
    </div>
  </transition-group>
</template>

<script lang="ts">
  export default {
      props: ['handlePlayer', 'move', 'cells','gameOver'],
  }
</script>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(4, 1fr);
  gap: 10px;
  justify-items: center;
  align-items: center;
  margin: 10px auto;
  width: 390px;
  height: 390px;
}

.cell {
  width: 90px;
  height: 90px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 10px;
  border: 3px solid #8bbda1;
  box-shadow: 3px 3px 3px rgba(0, 0, 0, 0.3);
  font-size: 40px;
  cursor: pointer;
  transition: 200ms all ease-in-out;
}

.cell:hover {
  border: 5px dashed rgb(17, 83, 11);
  box-shadow: none;
}
</style>