<template>
  <div id="app">
    <h1>Vue Calculator & API Demo</h1>
    <Calculator />
    <ApiData />
  </div>
</template>

<script setup>
import Calculator from './components/Calculator.vue';
import ApiData from './components/ApiData.vue';
</script>
<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    text-align: center;
  }
</style>