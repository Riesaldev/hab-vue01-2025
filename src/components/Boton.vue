<!-- PARTE LOGICA -->
<script setup>
defineProps({
    text: {
        type: String,
        required: true,
        default: '¡¡¡FALTA TEXT!!!'
    },
    onClick: {
        type: Function,
        required: true,
        default: () => {alert('FALTA FUNCION')}
    },
    className: {
        type: String,
        required: false,
        default: 'primary'
    },
    title: {
        type: String,
        required: false,
        default: 'Boton'
    }
})

</script>

<!--PARTE DEL RENDERIZADO -->
<template>
    <button @click="onClick" :class="className" :title="title">
        {{ text }}
    </button>
</template>

<!--PARTE DEL ESTILO -->
<style scoped> 
button {
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    background-color: #AAAAAA;
}
button:hover {
    background-color: #888888;
}
button:active {
    background-color: #AAAAAA;
}

.primary {
    background-color: #2c3dd8;
}
.primary:hover {
    background-color: #1928ad;
}
.primary:active {
    background-color: #2c3dd8;
}

.error {
    background-color: #FF0000;
}
.error:hover {
    background-color: #AA0000;
}
.error:active {
    background-color: #FF0000;
}



</style>
