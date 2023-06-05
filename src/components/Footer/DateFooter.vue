<template>
    <div class="current-date">
      Today is {{ currentDayOfWeek }}, {{ currentDay }}th of {{ currentMonth}}, {{ currentYear }}
    </div>
  </template>
  
<script lang="ts">
  export default {
    data() {
      return {
        currentDayOfWeek: null as null | string,
        currentDay: null as null | number,
        currentMonth: null as null | string,
        currentYear: null as null | number,
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
        this.currentDayOfWeek = currentDate.toLocaleString('en-US', { weekday: 'long' });
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