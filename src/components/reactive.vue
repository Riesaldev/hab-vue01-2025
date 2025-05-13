<script setup>
import { watch, reactive } from 'vue';

const personaje = reactive({
    nickname: 'Juan',
    parameters: {
        level: 20,
        health: 100,
        attack: 10,
        defense: 5,
        magic: 3,
        luck: 2,
    }
    
})

watch(
    () => personaje.parameters.level,
    (newLevel, oldLevel) => {
        console.log("NUEVO",newLevel,"ANTES",oldLevel);
    }
)

</script>   

<template>
    <div>
        <h1>Reactive</h1>
        <p>Nickname: {{ personaje.nickname }}</p>
        <p>Level: {{ personaje.level }}</p>
        <p>Health: {{ personaje.health }}</p>
        <p>Attack: {{ personaje.attack }}</p>
        <p>Defense: {{ personaje.defense }}</p>
        <p>Magic: {{ personaje.magic }}</p>
        <p>Luck: {{ personaje.luck }}</p>
        <button @click="personaje.level++">Incrementar nivel</button>
        <button @click="personaje.health++">Incrementar salud</button>
        <button @click="personaje.attack++">Incrementar ataque</button>
        <button @click="personaje.defense++">Incrementar defensa</button>
        <button @click="personaje.magic++">Incrementar magia</button>
        <button @click="personaje.luck++">Incrementar suerte</button>
    </div>
</template>

