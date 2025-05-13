<script setup>
import { ref, computed } from 'vue';


const catetoA = ref(0);
const catetoB = ref(0);

const hipotenusa = computed(() => {
    // Si el catetoA o el catetoB es 0, no se puede calcular la hipotenusa
    if (catetoA.value === 0 || catetoB.value === 0) {
        return "Ingrese valores a los catetos";
    }
    
    return Math.sqrt(catetoA.value ** 2 + catetoB.value ** 2);
});

</script>

<template>
    <div>
        <h1>Computed</h1>
        <input type="number" v-model.number="catetoA">
        <input type="number" v-model.number="catetoB">
        <p>La hipotenusa es: {{ hipotenusa }}</p>
    </div>
</template>

<style scoped>
input {
    margin: 10px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 16px;
    color: #333;
    background-color: #f5f5f5;
}
</style>

