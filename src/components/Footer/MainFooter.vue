<template>
    <DateFooter />
    <footer>Coded by <a href="https://www.lunasmithart.com/" target="_blank">Luna Smith</a>, open-sourced on 
    <a href="https://github.com/Lu-Smith/tic_tac_toe_vue" target="_blank">GitHub</a>.</footer>
</template>

<script>
import DateFooter from './DateFooter.vue';

export default {
  components: {
    DateFooter,
  },
}
</script>


  
  <style>
  footer {
      position: fixed;
      bottom: 0;
      right: 0;
      left: 0;
      text-align: center;
      padding: 20px;
      color: rgb(250, 250, 250);
  
  }
  
  footer a {
    color: rgb(215, 233, 241);
    text-decoration: none;
    position: relative;
    transition: color 0.3s;
  }
  
  footer a::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 2px;
    bottom: -5px;
    left: 0;
    background-color: rgb(121, 136, 185);
    visibility: hidden;
    transform: scaleX(0);
    transition: all 0.3s ease-in-out;
  }
  
  footer a:hover {
    color: rgb(121, 136, 185);
  }
  
  footer a:hover::before {
    visibility: visible;
    transform: scaleX(1);
  }
  </style>