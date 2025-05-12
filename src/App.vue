<script setup>
import { ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue'
import Boton from './components/Boton.vue'
import onBeforeMount from './components/onBeforeMount.vue'
import onMounted from './components/onMounted.vue'
import onBeforeUpdate from './components/onBeforeUpdate.vue'
import onUpdated from './components/onUpdated.vue'
import onBeforeUnmount from './components/onBeforeUnmount.vue'
import onUnmounted from './components/onUnmounted.vue'
import vText from './components/v-text.vue'
import vHtml from './components/v-html.vue'
import vShow from './components/v-show.vue'
import vFor from './components/v-for.vue'


const showOnBeforeUnmount = ref(true)
const showOnUnmounted = ref(true)

const handleShowOnBeforeUnmount = () => {
  showOnBeforeUnmount.value = !showOnBeforeUnmount.value
}

const handleShowOnUnmounted = () => {
  showOnUnmounted.value = !showOnUnmounted.value
}

const handleClick = () => {
  alert('Click en el boton desde el padre')
}

</script>

<template>
  <header>
    <vText />
    <vHtml />
    <vShow />
    <vFor />
  </header>

  <main>
    <Boton text="Boton Principal" :onClick="handleClick" className="primary" title="Boton Principal para acceder a la pagina" />
    <Boton text="Boton Error" :onClick="handleClick" className="error" />
    <Boton text="Boton Error" :onClick="handleClick" className="asdasd" />
    <onBeforeMount />
    <onMounted />
    <onBeforeUpdate />
    <onUpdated />
    
    <Boton text="Mostrar/Ocultar componente" :onClick="handleShowOnBeforeUnmount"/>
    <onBeforeUnmount v-if="showOnBeforeUnmount" />

    <Boton text="Mostrar/Ocultar componente" :onClick="handleShowOnUnmounted"/>
    <onUnmounted v-if="showOnUnmounted" />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: block;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
