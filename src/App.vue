<template>
  <div id="app">
      <Cliente :cliente="clienteSilas"/>
 
 //prop antiga
      <Cliente nome="Paulo Silveira" email="paulo@email.com.br" idade="51"/>
 
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
