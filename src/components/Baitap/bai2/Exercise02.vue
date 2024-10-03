<template>
    <div>
      <h1>Counter: {{ count }}</h1>
      <button @click="increment">Counter</button>
    </div>
  </template>
  
  <script setup>
  import { ref, watch } from 'vue';
  
  const count = ref(0);

  const increment = () => {
    count.value++;
  };
  
  watch(count, (newValue, oldValue) => {
    console.log('Dữ liệu đã thay đổi từ', oldValue, 'đến', newValue);
  });
  </script>
  
  <style scoped>
  
  </style>