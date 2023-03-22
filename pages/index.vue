<template>
  <div>
    <h1>Pagina Inicial</h1>
    <hr>
    <form action="" @submit.prevent="receberDados">
      <label for="nome">Nome:</label>
        <input type="text" name="nome" id="nome" v-model="inputNome">
        <button>Enviar</button>
    </form>
    <h1>Lista de contatos</h1>
    <ul v-for="ct in Object.keys(listaContato)">
      <li>Nome:<strong>{{listaContato[ct].nome}}</strong></li>
      <hr>
    </ul>
  </div>
</template>
<script>
  export default{
    data(){
      return{
        inputNome:"",
        listaContato: [
                {
                    "nome":"João",
                },
                {
                    "nome":"Pedro",
                }
            ]
      }
    },
    methods:{
      receberDados(){
        let dados = {
          nome: this.inputNome
        }
        this.listaContato.push(dados)
      }
    }
  }
</script>