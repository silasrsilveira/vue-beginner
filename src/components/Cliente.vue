<template>
<div :class="{'cliente': !isPremiun,'cliente-premiun': isPremiun}">
        <h4>Nome: {{cliente.nome}}</h4>
        <hr>
        <p>{{cliente.descricao}}</p>
        <hr>
        <p>Email: {{cliente.email}}</p>
        <p v-if="showIdade === true">Idade: {{cliente.idade}}</p>
        <p v-else>O usuario escondeu a Idade!</p>
       </div>
   
    
</template>


<script>
export default {
    data(){
        return {
            isPremiun: false,
            descricao: "As oportunidades só são aproveitadas se você estiver preparado!"
        }
    },

            props: {                
            cliente: Object,
            showIdade: Boolean
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