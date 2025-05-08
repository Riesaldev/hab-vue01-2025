<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Boton from './components/Boton.vue'

const handleClick = () => {
  alert('Click en el boton desde el padre')
}

</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="Hola HAB" />
    </div>
  </header>

  <main>
    <Boton text="Boton Principal" :onClick="handleClick" className="primary" title="Boton Principal para acceder a la pagina" />
    <Boton text="Boton Error" :onClick="handleClick" className="error" />
    <Boton text="Boton Error" :onClick="handleClick" className="asdasd" />
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
    display: flex;
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
