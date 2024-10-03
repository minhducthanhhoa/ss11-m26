<template>
  <div>
    <div v-if="isShow">
        <!-- <ChildrenComponent></ChildrenComponent> -->
         <Time></Time>
    </div>
    <h1>Parent Component</h1>
    <button @click="handleShow">toggle</button>
  </div>
</template>

<script setup>
    import { ref } from 'vue';
    import Time from './Time.vue';
    import ChildrenComponent from './ChildrenComponent.vue';
    const isShow = ref(false);
    const handleShow = ()=>{
        isShow.value = !isShow.value;
    }
</script>

<style>

</style>