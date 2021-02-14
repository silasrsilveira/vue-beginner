<template>
  <div id="app">
        <div v-for="(cliente,index) in clientes" :key="cliente.id">
          <h4>{{index + 1}}</h4>
            <Cliente :cliente="cliente"/>
            <hr>
            <h4>Edição: </h4>                  
            <input type="text" v-model="cliente.nome">
            <input type="text" v-model="cliente.email">
        </div>



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
        
      },
      clientes: [
        { 
          id: 1,            
              nome: "Silas Ribeiro",
              email: "silas@email.com.br" ,
              idade: 25
      },
    {
      id: 2,
              nome: "Paulo Junior",
              email: "paulo@email.com.br" ,
              idade: 24

      },
        
    { 
      id: 3,
              nome: "Isaias Santos",
              email: "isaias@email.com.br" ,
              idade: 26

          },
    { 
      id: 4,
              nome: "Eunice Costa",
              email: "nice@email.com.br" ,
              idade: 51

          },
    { 
      id: 5,
              nome: "Lidiane Ribeiro",
              email: "ldi@email.com.br" ,
              idade: 18

          },
        
        ]
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
