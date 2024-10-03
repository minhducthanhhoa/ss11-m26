<template>
    <div>
      <h1>Ứng dụng đếm số</h1>
      <p>Count: {{ count }}</p>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted, onBeforeUnmount } from 'vue';
  
  const count = ref(0);
  let intervalId;
  
  const incrementCount = () => {
    count.value += 3;
  };
  
  onMounted(() => {
    intervalId = setInterval(incrementCount, 3000);
  });
  
  onBeforeUnmount(() => {
    clearInterval(intervalId);
  });
  </script>
  
  <style scoped>
 
  </style>