<template>
    <div>
        <h1>Time: {{ time }}</h1>
    </div>
</template>

<script setup>
    import { onBeforeMount, onBeforeUnmount, onBeforeUpdate, onMounted, onUnmounted, onUpdated, ref } from 'vue';
    const time = ref(0);
    let timerId;
    // Giai đoạn mounting
    onBeforeMount(()=>{
        console.log("Before mount");
    })
    onMounted(()=>{
        setInterval(()=>{
            time.value++;
        }, 1000)
        console.log("Mounted");
    })
    
    // Giai đoạn updating
    onBeforeUpdate(()=>{
        console.log("Before update");
    })
    onUpdated(()=>{
        console.log("Updated");
    })

    // Giai đoạn unmount
    onBeforeUnmount(()=>{
        clearInterval(timerId);
        console.log("Before unmount");
    })
    onUnmounted(()=>{
        console.log("Unmounted");
    })
</script>

<style>

</style>