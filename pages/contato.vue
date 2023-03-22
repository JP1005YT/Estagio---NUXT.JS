<template>
    <h1>Pagina de Contato</h1>
    <FormularioContato
        @enviarDados="receberDados"
    />
    <hr>
    <p>Lista de contatos:</p>
    <ul v-for="ct in Object.keys(listaContato)">
        <li>Nome:<strong>{{listaContato[ct].nome}}</strong></li>
        <li>Email:<strong>{{listaContato[ct].email}}</strong></li>
        <li>Mensagem:<strong>{{listaContato[ct].msg}}</strong></li>
    </ul>
    <hr>
</template>
<script>
    export default {
        data(){
            return{
                listaContato: [
                {
                    "nome":"João",
                    "email":"godlolpro32@gmail.com",
                    "msg":"Mensagem...."
                },
                {
                    "nome":"Pedro",
                    "email":"godlolpro32@gmail.com",
                    "msg":"Mensagem...."
                }
            ]
            }
        },
        methods: {
                receberDados(dados){
                    this.listaContato.push(dados)
                }
            }
    }
</script>