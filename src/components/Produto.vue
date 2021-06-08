<template>
    <div>
        <h2>Meus Produtos</h2>
        <h3>Estes são meus produtos!</h3>
        <div>
            <!-- :key foi add por ter bug no for link:https://stackoverflow.com/questions/47608379/vue-language-server-elements-in-iteration-expect-to-have-v-bindkey-directiv-->
            <p v-for="produto in Produtos" :key="produto.id">
                {{produto.nome}} - R${{produto.valor}},00 
            </p>
            <hr>
        </div>
    </div>    
</template>

<script>
//export default: pq quando vc cria um componente, é necessário exportar para outros arquivos
export default  {
    data(){
        return{
            Produtos: [
                {nome: 'Celular', valor: 2500}, 
                {nome: 'TV', valor: 3800},
                {nome: 'Fogão', valor: 2417},
                {nome: 'Geladeira', valor: 5000}]
        }
    }
}
</script>

<!--scoped: tudo que for definido dentro da tag só será aplicado neste componente específico-->
<style scoped>
    
</style>