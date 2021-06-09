<template>
<!--para mais de uma tag, utilize div 
um componente só pode ter uma tag raiz-->
    <div id="cliente">
        <!-- :value é utilizado para receber uma variavel do script - data binding - não é possível alterar o dado
        <input type="text" :value="nome">
        <input type="text" :value="idade">-->

        <!-- v-model é utilizado para receber uma variavel do script e modificar em tempo real- two way data binding
        <input type="text" v-model="nome">
        <input type="text" v-model="idade">
        <h2>Cliente: {{ nome }}</h2>
        <h3>Idade: {{idade}} </h3>
        função jscript 
        {{2 + 2 * 2}}-->

        <!--recebendo valor do objeto cliente
        <h4>Nome: {{cliente.nome}}</h4>
        <hr>
        <p>{{descricao}}</p>
        <p>Número: {{numero}}</p>
        <p>Email: {{cliente.email}}</p>
        <p>Idade: {{cliente.idade}}</p>
        
        Prever o comportamente do submit
        <form v-on:submit.prevent="alterarTexto('Teste')">
            <input type="text" v-model="escreveAqui"/>
        </form>

        Só muda o texto dentro do input quando der um enter-->
        <input type="text" v-model="escreveAqui" v-on:keyup.enter="alterarTexto()"/>

        <ul>
            <li v-for="nome in arrayTeste" :key="nome.id" @click="alerta">
                {{nome}}
                <hr>
            </li>
        </ul>
    </div>
</template>

<script>
//export default: pq quando vc cria um componente, é necessário exportar para outros arquivos
export default  {
    data(){
        return {
            /*nome: "Dainara",
            numero: "45984313550",
            email: "dainarakrewer@cloudcrm.tech",
            idade: 22,
            descricao: "Uma descrição aqui!"*/
            escreveAqui: "",
            arrayTeste: []
        }
    },
    props: {
        //define o tipo da variavel que será recebida, só pode ter uma var nome
        nome: String,
        email: String,
        idade: Number,
        //tipo objeto
        cliente: Object
    },
    methods: {
        alterarTexto(/*nome*/){
            //this.escreveAqui = nome;
            //ao clicar em enter, add o valor passado para o array
            this.arrayTeste.push(this.escreveAqui);
            //limpa o input
            this.escreveAqui = '';
        },
        alerta(event){
            //ao clicar no input add, traz o valor do input
            alert(event.target.textContent.trim());
        }
    }
}
</script>

<!--scoped: tudo que for definido dentro da tag só será aplicado neste componente específico-->
<style scoped>
    #cliente {
        color: #343a40;
        background-color: #fec5bb;
        font-family: 'Poppins', sans-serif;
        padding: 4px;
        text-align: center;
    }

</style>