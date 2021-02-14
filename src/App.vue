<template>
  <div id="app">

                <h3>Cadastro de Clientes</h3>

                <small id="nomeErro" v-show="deuErro">O nome é inválido, tente novamente!</small> <br>

                <input type="text" placeholder="nome" v-model="nomeField"><br>
                <input type="text" placeholder="email" v-model="emailField"><br>
                <input type="text" placeholder="idade" v-model="idadeField"><br>
                <button @click="cadastrarUsuarios">Cadastrar</button>

        <div v-for="(cliente,index) in orderClientes" :key="cliente.id">
          <h4>{{index + 1}}</h4>
            <Cliente :cliente="cliente" @meDelete="deletarUsuario($event)"/>
            <hr>
            <h4>Edição: </h4>                  

        </div>

     </div>
</template>

<script>
import _ from 'lodash';
import Cliente from './components/Cliente';
export default {
    name: 'App',
    data(){
      return{
        deuErro: false,
        nomeField: "",
        emailField: "",
        idadeField: "",
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
       } 
     ]
    }
  },
          components: {
      Cliente,

  },
          methods: {
           
          cadastrarUsuarios: function(){
             if (this.nomeField == "" || this.nomeField == " " || this.nomeField.length < 3) {
              this.deuErro = true
            }else{
          this.clientes.push({nome: this.nomeField, email: this.emailField, idade: this.emailField, id: Date.now()})
          this.nomeField = "",
          this.emailField = "",
          this.idadeField = 0
          this.deuErro = false
       }
      },
        deletarUsuario: function($event){
        console.log("Recebendo Evento!");
        var id = $event.idDoCliente;
        var novoArray = this.clientes.filter(cliente => cliente.id != id)
        this.clientes = novoArray;
      }
     },

     computed: {
       orderClientes: function(){
         return _.orderBy(this.clientes, ['nome'], ['asc'])

       }
     }
     
  } 

</script>
    
<style>

  #nomeErro{
    color: red
  }


</style>
