<script setup>
import { ref } from 'vue';
import Boton from './Boton.vue';

const show = ref(true)

const handleShow = () => {
    show.value = !show.value
}
</script>

<template>
    <div>
        <Boton text="Mostrar/Ocultar" :onClick="handleShow" />
        <h1 v-show="show">Hola Mundo V-SHOW</h1>
    </div>
</template>


