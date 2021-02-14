<template>
<div :class="{'cliente': !isPremium,'cliente-premiun': isPremium}">
        <h4>Nome: {{cliente.nome}}</h4>
        <hr>
        <p>{{cliente.descricao}}</p>
        <hr>
        <p>Email: {{cliente.email | processarEmail}}</p>
        <p v-if="showIdade === true">Idade: {{cliente.idade}}</p>
        <p v-else>O usuario escondeu a Idade!</p>

    <button @click="mudarCor($event)">Mudar cor!</button>
    <button @click="emitirEventoDelete">Deletar</button>

       </div>
   
    
</template>


<script>
export default {
    data(){
        return {
            isPremium: false,
            descricao: "As oportunidades só são aproveitadas se você estiver preparado!"
        }
    },

            props: {                
            cliente: Object,
            showIdade: Boolean
        },

            methods: {
            mudarCor: function($event){
            console.log($event);
            this.isPremium =  !this.isPremium
        },
                emitirEventoDelete: function (){
                console.log("Emitindo do Filho");
                this.$emit("meDelete", {idDoCliente: this.cliente.id,curso: "node js", component:this});
            },

            testar: function(){
                console.log("Testando para valer");
                alert("Isso é um alert!")

            }
        },
        filters:{
       processarEmail: function(value){
         return value.toUpperCase();
       }
     }
}

</script>



<style scoped>
    .cliente{
     background: #E8E6EA;
     height: 240px;
     padding: 1%;
     margin-top: 2%;
    }
    
    .cliente-premiun{
     background: rgb(24, 23, 23);
     color: yellow;
     height: 240px;
     padding: 1%;
     margin-top: 2%;
    }

</style>