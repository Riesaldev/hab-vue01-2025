<script setup>
import { onUpdated, ref } from 'vue';
import Boton from './Boton.vue'

const msg = ref("Texto inicial")


const updateMsg = () => {
    msg.value = "Texto actualizado"
}

onUpdated(()=>{
    console.log("onUpdated", msg.value)
    const input = document.getElementById("segundoInput")
    if(input){
        input.focus()
    }
})


</script>


<template>
    <div>
        <h1>onUpdated data</h1>
        <p>{{ msg }}</p>
        <input type="text" id="segundoInput" v-if="msg === 'Texto actualizado'" />
        <Boton text="Actualizar" :onClick="updateMsg" className="primary" />
    </div>
</template>


<style scoped>
</style>
