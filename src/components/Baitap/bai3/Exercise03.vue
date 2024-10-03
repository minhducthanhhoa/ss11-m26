<template>
    <div>
      <div>
        Current Company: {{ company }}
      </div>
      <div>
        Age: {{ age }}
      </div>
      <button @click="randomAge">Random</button>
    </div>
  </template>
  
  <script setup>
  import { ref } from "vue";
  
  const age = ref(1);
  const companies = ref(["Rikkei Academy", "Rikkei Education", "Rikkei Fukuoka"]);
  const company = ref("Rikkei Academy");
  
  const randomAge = () => {
    age.value = Math.floor(Math.random() * 10) + 1;
    company.value = companies.value[age.value % 3];
  };
  </script>