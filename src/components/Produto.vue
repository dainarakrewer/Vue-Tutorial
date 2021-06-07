<template>
    <div>
        <h2>Meus Produtos</h2>
        <h3>Estes são meus produtos!</h3>
        <div>
            <!-- :key foi add por ter bug no for link:https://stackoverflow.com/questions/47608379/vue-language-server-elements-in-iteration-expect-to-have-v-bindkey-directiv-->
            <p v-for="produto in Produtos" :key="produto.id">{{produto}}</p>
        </div>
    </div>    
</template>

<script>
//export default: pq quando vc cria um componente, é necessário exportar para outros arquivos
export default  {
    data(){
        return{
            Produtos: ['Celular', 'TV', 'Fogão', 'Geladeira']
        }
    }
}
</script>

<!--scoped: tudo que for definido dentro da tag só será aplicado neste componente específico-->
<style scoped>
    
</style>