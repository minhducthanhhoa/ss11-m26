<template>
    <div>
      <h1>Parent Component</h1>
      <p>Age: {{ age }}</p>
      <button @click="increaseAge">Increase age</button>
      <Children :age="age" />
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import Children from './Children.vue';
  
  const age = ref(0);
  
  const increaseAge = () => {
    age.value += 1;
  };
  </script>
  
  <style scoped>
  
  </style>