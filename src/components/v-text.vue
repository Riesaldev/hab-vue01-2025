<script setup>
import { ref } from 'vue';
import Boton from './Boton.vue';

const nombre = ref('Juan')

const handleChangeMsg = () => {
    nombre.value = 'Pedro'
}
</script>

<template>
<div>
    <p><span>Hola {{ nombre }}</span></p>
    <p><span v-text="nombre"></span> (usando v-text)</p>
    <Boton text="Cambiar mensaje" :onClick="handleChangeMsg" />
</div>
</template>



<style scoped>

</style>
