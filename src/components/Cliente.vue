<template>
<div id="cliente">

    <input type="text" :model="nome">
    <hr>
    <input type="text" v-model="descricao">

    
    <h2 id="cliente-nome">{{nome}}, {{numero}}</h2>
    <h3>{{descricao}}</h3>
   

    </div>
   
    
</template>


<script>
export default {
    data(){
        return {
            nome: "Silas Ribeiro da Silveira",
            numero: "992179862",
            email: "",
            idade: 0, 
            descricao: "Lorem ipsum Lorem Ipsum"
        }
    }
}


</script>


<style scoped>
    #cliente{
     
    }
    #cliente-nome{
            }
    

</style>