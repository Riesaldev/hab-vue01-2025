<script setup>
import { onUnmounted } from 'vue';

onUnmounted(()=>{
    console.log('onUnmounted')
})
</script>

<template>
    <div>
        <h1>onUnmounted</h1>
    </div>
</template>

<style scoped>
</style>