<template>
  <div>
    <h1>Children component</h1>
    <h2>Count: {{ count }}</h2>
    <button @click="handleIncrease">Count</button>
    <input type="text" v-model="inputValue">
  </div>
</template>

<script setup>
    import { onBeforeMount, onBeforeUnmount, onBeforeUpdate, onMounted, onUpdated, ref } from 'vue';
    const count = ref(0);
    const inputValue = ref("");
    // Các phương thức trong giai đoạn mounting
    onBeforeMount(()=>{
        // count.value = 5;
        console.log("Before mount");
    })
    onMounted(()=>{
        // count.value = 6;
        console.log("Mounted");
    })
    // Các phương thức trong giai đoạn updation 
    onBeforeUpdate(()=>{
        console.log("Before update");
        document.title = inputValue.value;
    })
    onUpdated(()=>{
        console.log("Updateed");
        inputValue.value = "Nguyễn Văn A"
    })
    const handleIncrease = ()=>{
        count.value++;
    }
    // Các phương thức trong giai đoạn unmoubt 
    onBeforeUnmount(()=>{
        console.log("Before Unmount");
    })
    onMounted(()=>{
        console.log("Mount");
    })
</script>

<style>

</style>