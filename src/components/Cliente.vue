<template>
<!--para mais de uma tag, utilize div 
um componente só pode ter uma tag raiz-->
    <div id="cliente">
        <!-- :value é utilizado para receber uma variavel do script - data binding - não é possível alterar o dado
        <input type="text" :value="nome">
        <input type="text" :value="idade">-->

        <!-- v-model é utilizado para receber uma variavel do script e modificar em tempo real- two way data binding -->
        <input type="text" v-model="nome">
        <input type="text" v-model="idade">
        <h2>Cliente: {{ nome }}</h2>
        <h3>Idade: {{idade}} </h3>
        <!--função jscript 
        {{2 + 2 * 2}}-->
    </div>
</template>

<script>
//export default: pq quando vc cria um componente, é necessário exportar para outros arquivos
export default  {
    data(){
        return {
            nome: "Dainara",
            numero: "",
            email: "",
            idade: 22
        }
    }
}
</script>

<!--scoped: tudo que for definido dentro da tag só será aplicado neste componente específico-->
<style scoped>
    #cliente {
        color: #b5838d;
    }
</style>