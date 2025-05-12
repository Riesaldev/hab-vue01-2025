<script setup>
import { onMounted, ref } from 'vue';

const data = ref(null)

onMounted(async ()=>{
    try {
        data.value = {text:'Esperando datos...'}
        await new Promise(resolve => setTimeout(resolve, 3000));
        const response = await fetch('https://jsonplaceholder.typicode.com/todos/1')
        data.value = await response.json()
    } catch (error) {
        console.error('Error fetching data:', error)
    }
})

</script>

<template>
    <div>
        <h1>onMounted data</h1>
        <pre>{{ data }}</pre>
    </div>
</template>

<style scoped>
</style>


