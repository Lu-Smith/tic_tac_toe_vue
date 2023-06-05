<template>
    <div class="current-date">
      Today is {{ currentDay }}th of {{ currentMonth}}, {{ currentYear }}
    </div>
  </template>
  
<script>
  export default {
    data() {
      return {
        currentDay: null,
        currentMonth: null,
        currentYear: null,
        months: ['January', 'February', 'March', 'April', 'May','June', 'July', 'August', 'September', 'October', 'November', 'December'],
      };
    },
    mounted() {
      this.getCurrentDate();
    },
    methods: {
      getCurrentDate() {
        const currentDate = new Date();
        this.currentDay = currentDate.getDate();
        this.currentMonth = this.months[currentDate.getMonth()];
        this.currentYear = currentDate.getFullYear();
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