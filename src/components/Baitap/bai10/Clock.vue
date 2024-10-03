<template>
    <div>
      <h1>Thời gian hiện tại: {{ currentTime }}</h1>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted, onBeforeUnmount } from 'vue';
  
  const currentTime = ref('');
  
  const updateTime = () => {
    const now = new Date();
    currentTime.value = now.toLocaleTimeString(); 
  };
  
  let intervalId;
  
  onMounted(() => {
    updateTime(); 
    intervalId = setInterval(updateTime, 1000); 
  });
  
  onBeforeUnmount(() => {
    clearInterval(intervalId); 
  });
  </script>
  
  <style scoped>

  </style>