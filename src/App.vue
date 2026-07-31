<template>
  <VantaBackground>
    <Header />
    <Landing />
  </VantaBackground>
</template>

<script setup lang="ts">
  import Header from './components/Header.vue';
  import Landing from './components/sections/Landing.vue';
  import VantaBackground from './components/VantaBackground.vue';
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Alata&display=swap');
  @import "tailwindcss";
  
  body {
    font-family: 'Alata', sans-serif;
  }

  .background-black {
    background-color: rgba(0, 23, 31, 0.75);
  }

  .font-white {
    color: #E2E2E2;
  }
</style>
