<script setup>
import { ref } from 'vue';

const calificacion = ref(0);
const alt = ref('Input para calificar');
</script>

<template>
    <div>
        <h1>V-IF</h1>
        <p>Calificación: {{ calificacion }}</p>
        <input type="number" min="0" max="10" v-model.number="calificacion"  :title="alt"/>
        <p v-if="calificacion >= 9" class="excelente">Excelete!!!</p>
        <p v-else-if="calificacion >= 5" class="aprobado">Aprobado</p>
        <p v-else-if="calificacion >= 3" class="desaprobado">Desaprobado</p>
        <p v-else class="reprobado">Reprobado</p>
        
    </div>
</template>

<style scoped>
.excelente {
    color: green;
    font-weight: bold;
    background-color: white;
}
.aprobado {
    color: green;
}
.desaprobado {
    color: yellow;
}
.reprobado {
    color: red;
}
</style>    
