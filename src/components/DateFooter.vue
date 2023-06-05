<template>
    <div>
      Current Date: {{ currentDate }}
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