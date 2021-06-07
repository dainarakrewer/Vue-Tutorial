<template>
  <div id="app">
    <!--<h1>Guia do Programador!</h1>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <h1>Guia Clientes</h1>
    <!--componente sendo usado-->
    <!-- parametro para o componente 
    <input type="text" v-model="nomeDainara">
    <Cliente :nome="nomeDainara" email="dainara@teste.com" idade="22"/>-->
    <!-- recebendo uma var de um array
    <input type="text" v-model="clienteDainara.nome">-->
    <!-- criando um campo de digitação para que dependendo do que foi digitado, aparece a div referente
    IMPORTANTE: Está sem <hr> dps da primeira div pois o if n funciona com <hr>
    <input type="text" v-model="texto">
    <hr>
    <div v-if="texto == 'Dainara'">
      <Cliente :cliente="clienteDainara"/>
    </div>
    <div v-else-if="texto == 'João'">
      <Cliente :cliente="clienteJoao"/> 
    </div> 
    <div v-else>
      <Cliente :cliente="clienteDainara"/>
      <hr>
      <Cliente :cliente="clienteJoao"/> 
    </div> -->
    <div id="dainara">
      <Cliente :cliente="clienteDainara"/>
    </div><!--
    --><div  id = "joao">
      <Cliente :cliente="clienteJoao"/> 
    </div>
    <!-- prop para preencher var manual
    <Cliente nome="Maria" email="maria@teste.com" idade="18"/>-->
    <hr>
    <Produto />
  </div>
</template>


<script>
/*import HelloWorld from './components/HelloWorld.vue'*/
//import: componente está sendo importado
import Cliente from './components/Cliente'
import Produto from './components/Produto'
export default {
  name: 'App',
  data(){
    return{
      // var para parametro do if
      //texto: "",
      //var para passar como parametro no componente
      //nomeDainara: "Dainara",
      clienteJoao: {
        nome: "João",
        email: "joao@teste.com",
        idade: 20
      },

    clienteDainara: {
      nome: "Dainara",
      email: "dainara@teste.com",
      idade: 20
    }
    }
  },
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
    background-color: #f8edeb;
    /*margin-right: -9px;*/
    margin: -8px;
    padding: 4px;
    text-align: center;
  }
</style>
