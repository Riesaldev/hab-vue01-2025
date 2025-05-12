<script setup>
import { onBeforeUpdate, ref } from 'vue';
import Boton from './Boton.vue'

const count = ref(0)

const increment = () => {
    count.value++
}

onBeforeUpdate(()=>{
    console.log('onBeforeUpdate', count.value)
})

</script>

<template>
    <div>
        <h1>onBeforeUpdate data</h1>
        <p>{{ count }}</p>
        <Boton text="Incrementar" :onClick="increment" className="primary" />
    </div>
</template>

<style scoped>
</style>
