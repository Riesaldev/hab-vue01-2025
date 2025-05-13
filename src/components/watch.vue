<script setup>
import { ref, watch } from 'vue';

const name = ref('Juan');
const lastName = ref('Perez');

watch([name, lastName], ([newName,newLastName], [oldName,oldLastName]) => {
    console.log("NUEVO",newName,newLastName,"ANTES",oldName,oldLastName);
})


</script>   

<template>
    <div>
        <h1>Watch</h1>
        <input type="text" v-model="name">
        <input type="text" v-model="lastName">
    </div>
</template>

