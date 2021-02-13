<template>
  <div id="app">
      
 <input type="text" v-model="clienteSilas.nome">
 <input type="text" v-model="clienteSilas.email">
      <Cliente nome="Paulo Silveira" email="paulo@email.com.br" idade="51"/>
      <Cliente :cliente="clienteSilas" :showIdade="true"/>
      <Cliente :cliente="clienteSilas" :showIdade="true"/>
      <Cliente :cliente="clienteSilas" :showIdade="false"/>
      <Cliente :cliente="clienteSilas" :showIdade="false"/>
     </div>
</template>

<script>
import Cliente from './components/Cliente';
//import Produto from './components/Produto';
export default {
  name: 'App',
  data(){
    return{
      nomeDoSilas: "Silas R. Silveira",
      clienteSilas: {
        nome: "Silas Ribeiro",
        email: "silas@email.com.br" ,
        idade: 25,
        numero: 2021

      }
    }
  },
  components: {
    Cliente,
    //Produto
  }
}

</script>
    
<style>

</style>
