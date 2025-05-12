<script setup>
import { onBeforeUnmount, onMounted } from 'vue';

let interval = null;

onMounted(()=>{
    interval = setInterval(()=>{
        console.log('interval en ejecución')
    }, 1000)
})

onBeforeUnmount(()=>{
    console.log('onBeforeUnmount', interval)
    clearInterval(interval)
})
</script>

<template>
    <div>
        <h1>onBeforeUnmount</h1>
    </div>
</template>

<style scoped>
</style>
