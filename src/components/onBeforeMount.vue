<script setup>
import { onBeforeMount, ref } from 'vue';

const msg = ref('Hola Mundo antes de montar')

onBeforeMount(() => {
    console.log('onBeforeMount:', msg.value)
    msg.value = "Hola Mundo despues de montar"
    console.log('onBeforeMount2:', msg.value)
})
</script>

<template>
    <div>
        {{ msg }}
    </div>
</template>

<style scoped>
</style>
