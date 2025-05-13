<script setup>
import { ref } from 'vue';


const handleEnviar = () => {
    console.log('Enviar');
}

const handleDivClick = () => {
    console.log('Click en el div');
}

const handleBotonClick = () => {
    console.log('Click en el boton');
}

const handleEnter = () => {
    console.log('Enter');
}

</script>

<template>
    <div>
        <h1>V-ON</h1>
        <form @submit.prevent="handleEnviar">
            <input type="text" placeholder="Ingresar datos">
            <button type="submit">Enviar</button>
        </form>
        <div @click="handleDivClick" style="border: 1px solid red; padding: 20px;">
            Haz click aqui (en el div)
            <button @click.stop="handleBotonClick">
                Haz click aqui (en el boton)
            </button>
        </div>
        <input type="text" @keyup.enter="handleEnter">
    </div>
</template>
