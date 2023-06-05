<template>
    <div class="current-date">
      Today is {{ currentDate }}
    </div>
  </template>
  
<script>
  export default {
    data() {
      return {
        currentDate: null
      };
    },
    mounted() {
      this.getCurrentDate();
    },
    methods: {
      getCurrentDate() {
        this.currentDate = new Date().toLocaleDateString();
      }
    }
  };
</script>

<style>
.current-date {
  position: fixed;
  right: 30px;
  top: 20px;
  color: white;
}

</style>