<template>
    <form action="" @submit.prevent="receberDados">
        <label for="nome">Nome:</label>
        <input type="text" name="nome" id="nome" v-model="inputNome">
        <br><br>
        <label for="email">Email:</label>
        <input type="text" name="email" id="email" v-model="inputEmail">
        <br><br>
        <label for="mensagem">Mensagem</label>
        <textarea type="text" name="mensagem" id="mensagem" v-model="inputMesagem"></textarea>
        <br><br>
        <button>Enviar</button>
    </form>
</template>
<script>
export default{
    data(){
        return{
            inputNome: "Joao",
            inputEmail: "joao@joao",
            inputMesagem: "seila"
        }
    },
    methods:{
        receberDados(){
            const dados = {
                nome: this.inputNome,
                email: this.inputEmail,
                msg: this.inputMesagem,
            }
            this.$emit('enviarDados',dados)
        }
    }
}
</script>