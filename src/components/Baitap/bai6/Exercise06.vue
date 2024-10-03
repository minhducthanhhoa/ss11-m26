<template>
    <div>
      <h1>Current Count: {{ count }}</h1>
      <button @click="increment">Increment</button>
    </div>
  </template>
  
  <script setup>
  import { ref, watch } from 'vue';
  
  const count = ref(0);
  
  const increment = () => {
    count.value += 1;
  };
  
  watch(count, (newVal) => {
    document.title = `Count: ${newVal}`;
  });
  </script>
  
  <style scoped>
  
  </style>