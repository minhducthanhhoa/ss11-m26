<template>
    <div>
      <h1>Change Browser Tab Title</h1>
      <input v-model="title" placeholder="Enter new title" />
    </div>
  </template>
  
  <script setup>
  import { ref, watch, onMounted, onBeforeUnmount } from 'vue';
  
  const title = ref('');
  
  onMounted(() => {
    document.title = title.value;
  });
  
  watch(title, (newVal) => {
    document.title = newVal;
  });
  
  onBeforeUnmount(() => {
    document.title = 'Default Title'; 
  });
  </script>
  
  <style scoped>

  </style>