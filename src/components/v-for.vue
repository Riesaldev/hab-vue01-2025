<script setup>
import { ref } from 'vue';

const alumnos = ref([
    { id: 1, name: 'Ricardo', age: 20 },
    { id: 2, name: 'Rodrigo', age: 21},
    { id: 3, name: 'Emiliano', age: 22 }])
</script>

<template>
    <div>
        <h1>V-FOR</h1>
        <ul>
            <li v-for="a in alumnos" :key="a.id" >Nombre: {{a.name}} - Edad: {{a.age}} </li>
        </ul>
    </div>
</template>
