<script setup>
//Importamos REF para crear una referencia mutable (un estado)
import { ref } from 'vue';


//Creamos una referencia mutable (un estado) para el listado de alumnos
//Cada alumno debe tener el parámetro "mostrar" que indica si se debe mostrar o no
const alumnos = ref([
    {nombre:"Juan", edad:22, mostrar:true},
    {nombre:"Maria", edad:25, mostrar:true},
    {nombre:"Ana", edad:30, mostrar:true},
    {nombre:"Ricardo", edad:31, mostrar:true},
    {nombre:"Cristina", edad:28, mostrar:true},
])

//Creamos una función para mostrar todos los alumnos
//Recorremos el listado y a todos los alumnos les ponemos el parámetro "mostrar" a true
const handleMostrarTodos = () => {
    alumnos.value.forEach(a => a.mostrar = true)
}

//Creamos una función para ocultar todos los alumnos
//Recorremos el listado y a todos los alumnos les ponemos el parámetro "mostrar" a false
const handleOcultarTodos = () => {
    alumnos.value.forEach(a => a.mostrar = false)
}
</script>

<template>
    <div>
        <h1>Ejercicio 1</h1>
        <ul>
            <!-- Creamos con la directiva v-for un bucle que recorre el listado de alumnos -->
            <!-- Con la directiva v-show mostramos los alumnos que tienen el parámetro "mostrar" a true -->
            <li v-for="a in alumnos" :key="a.nombre" v-show="a.mostrar">
                {{a.nombre}} - {{a.edad}} 
                <!-- Creamos un botón que al hacer click cambia el parámetro "mostrar" a false -->
                <button @click="a.mostrar = false">Ocultar</button>
            </li>
        </ul>
        <!-- Creamos un botón que al hacer click muestra todos los alumnos -->  
        <button @click="handleMostrarTodos">Mostrar Todos</button>
        <!-- Creamos un botón que al hacer click oculta todos los alumnos -->
        <button @click="handleOcultarTodos">Ocultar Todos</button>
    </div>
</template>
 

<style scoped>

</style>