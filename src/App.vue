<template>
  <div id="app">
    <!--<h1>Guia do Programador!</h1>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <h1>Guia Clientes</h1>
    <!--componente sendo usado-->
    <Cliente/>
    <hr>
    <Produto/>
  </div>
</template>

<script>
/*import HelloWorld from './components/HelloWorld.vue'*/
//import: componente está sendo importado
import Cliente from './components/Cliente'
import Produto from './components/Produto'
export default {
  name: 'App',
  //componente foi setado
  components: {
    Cliente,
    Produto
  }
}
</script>

<style>
  #app {
    color: #6d6875;
  }
</style>
