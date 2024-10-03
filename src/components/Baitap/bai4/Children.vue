<template>
    <div>
      <h2>Children Component</h2>
    </div>
  </template>
  
  <script setup>
  import { defineProps, watch } from 'vue';
  
  const props = defineProps({
    age: {
      type: Number,
      required: true,
    },
  });
  
  watch(() => props.age, (newVal, oldVal) => {
    alert(`Giá trị của biến age đã thay đổi từ ${oldVal} thành ${newVal}`);
  });
  </script>
  
  <style scoped>

  </style>