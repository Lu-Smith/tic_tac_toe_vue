<template>
  <div class="grid">
    <div class="cell" v-for="(cell, index) in cells" :key="index"  @click="handlePlayer(index)">
    {{ cell }}
    </div>
  </div>
</template>

<script>
  export default {
      props: ['handlePlayer', 'move', 'cells'],
  }
</script>

<style>
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(3, 1fr);
  gap: 10px;
  justify-items: center;
  align-items: center;
  margin: 30px auto;
  width: 290px;
  height: 290px;
}

.cell {
  width: 90px;
  height: 90px;
  background: radial-gradient(circle at 10% 20%, rgb(253, 239, 132) 0%, rgb(247, 198, 169) 54.2%, rgb(21, 186, 196) 100.3%);
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 10px;
  border: 3px solid rgb(243, 184, 96);
  box-shadow: 3px 3px 3px rgba(0, 0, 0, 0.3);
}
</style>