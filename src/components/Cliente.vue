<template>
<div id="cliente">
        <h4>Nome: {{cliente.nome}}</h4>
        <hr>
        <p>{{cliente.descricao}}</p>
        <hr>
        <p>Numero: {{cliente.numero}}</p>
        <p>Email: {{cliente.email}}</p>
        <p>Idade: {{cliente.idade}}</p>
       </div>
   
    
</template>


<script>
export default {
    data(){
        return {
            descricao: "As oportunidades só são aproveitadas se você estiver preparado!"
        }
    },

            props: {
            nome: String,
            email: String,
            idade: Number,
            cliente: Object
        }
}

</script>



<style scoped>
    #cliente{
     background: #E8E6EA;
     height: 240px;
     padding: 1%;
     margin-top: 2%;
    }
    
    

</style>