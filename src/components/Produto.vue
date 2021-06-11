<template>
    <div>
        <h2>Meus Produtos</h2>
        <h3>Estes são meus produtos!</h3>
        <div>
            <!-- :key foi add por ter bug no for link:https://stackoverflow.com/questions/47608379/vue-language-server-elements-in-iteration-expect-to-have-v-bindkey-directiv-->
            <p v-for="produto in Produtos" :key="produto.id" >
                {{produto.nome}} - R${{produto.valor}},00 
                <!-- tentativa falha de fazer o texto ficar da cor repassado no Produtos 
                <input @click="corP($event.target.id)" type="radio" name="cor" :id="produto.cor"> {{produto.cor}}-->
            </p>
            <hr>
            <!-- v-bind:class="{red: colors.vermelho, green: colors.verde, blue: colors.azul, yellow: colors.amarelo}" 
            ref: dando um nome ao p (como um id) para utilizar o CSS-->
            <p ref="teste"> 
                Mude a cor aqui!
            </p>

            <button @click="vermelho()">Vermelho</button>
            <button @click="verde()">Verde</button>
            <button @click="azul()">Azul</button>
            <button @click="amarelo()">Amarelo</button>
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
                {nome: 'Celular', valor: 2500, /*cor:'red'*/}, 
                {nome: 'TV', valor: 3800, /*cor: 'green'*/},
                {nome: 'Fogão', valor: 2417, /*cor: 'blue'*/},
                {nome: 'Geladeira', valor: 5000, /*cor:'yellow'*/}],
            
            /*v-bind: class e mudança de cor q fracassou
            colors: {
                vermelho: false,
                verde:false,
                azul: false,
                amarelo: false
            }*/
                //classProduto: 'white'
        }
    },
    methods: {
    /*corP(){
            this.classProduto = "Produtos.cor";
        }
         v-bind: class e mudança de cor q fracassou*/
            vermelho(){
                /*
                this.colors.vermelho = true;
                this.colors.verde = false;
                this.colors.azul = false;
                this.colors.amarelo = false;*/
                //para acessar as referencias, utilizar $
                //definindo que a cor do texto vai ser vermelho (neste caso)
                this.$refs.teste.style.color = "red";
            },
            verde(){
                /*this.colors.vermelho = false;
                this.colors.verde = true;
                this.colors.azul = false;
                this.colors.amarelo = false;*/
                this.$refs.teste.style.color = "green";
            },
            azul(){
                /*this.colors.vermelho = false;
                this.colors.verde = false;
                this.colors.amarelo = false;
                this.colors.azul = true;*/
                this.$refs.teste.style.color = "blue";
            },
            amarelo(){
                /*this.colors.vermelho = false;
                this.colors.verde = false;
                this.colors.azul = false;
                this.colors.amarelo = true;*/
                this.$refs.teste.style.color = "yellow";
            }
    }
}
</script>

<!--scoped: tudo que for definido dentro da tag só será aplicado neste componente específico-->
<style scoped>

    /* v-bind: class e mudança de cor q fracassou
    .red{
        color: red;
    }

    .green{
        color: green;
    }

    .blue{
        color: blue;
    }   

    .yellow{
        color: yellow;
    }*/ 
</style>