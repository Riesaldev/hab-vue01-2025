<script setup>
import { ref } from 'vue';

const html = ref('<h1>Hola Mundo</h1>')
</script>


<template>
    <div>
        <div>{{ html }}</div>
        <div v-html="html"></div>
    </div>
</template>


