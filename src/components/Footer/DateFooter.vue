<template>
    <div class="current-date">
      Today is <span>{{ currentDayOfWeek }}</span>, {{ date }}
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
        date: '' as string
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
        if (this.currentDay === 1 || this.currentDay === 31) {
          this.date = `${this.currentDay}st of ${this.currentMonth}, ${this.currentYear}`;
        } else  if (this.currentDay === 2) {
          this.date = `${this.currentDay}nd of ${this.currentMonth}, ${this.currentYear}`;
        } else  if (this.currentDay === 3) {
          this.date = `${this.currentDay}rd of ${this.currentMonth}, ${this.currentYear}`;
        } else {
          this.date = `${this.currentDay}th of ${this.currentMonth}, ${this.currentYear}`;
        }
        
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
  font-size: 16px;
  line-height: 20px;
  font-style: italic;
}

.current-date span {
  color: rgb(236, 171, 193);
  font-weight: bold;
}

@media screen and (max-width: 480px) {
  .current-date {
    font-size: 12px;
    right: 20px;
    top: 13px;
  }
}
</style>