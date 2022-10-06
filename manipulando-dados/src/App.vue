<template>
    <p>{{ total }}</p>

    <button @click="calcula('-')"> - </button>
    <button @click="calcula('+')"> + </button>
    <br>
    <hr>
    <p>Nome Computado: {{ nomeFormatado }}</p>
    <label>Input a computar</label>
    <input v-model="nome" type="text">
    <br>
    <hr>
    <p>Nome Computado: {{ nomeFunction }}</p>
    <input v-model="nomeFunction" type="text">
    <br>
    <hr>
    <label>Input a observar</label>
    <input v-model="busca" type="text">
    <p v-text="resultado"></p>
</template>

<script>
export default {
    name: 'App',
    data() {
        return {
            total: 10,
            nome: 'jose antonio',
            resultado: '',
            busca: ''
        }
    },
    watch: {
        busca: function () {
            this.resultado = 'Aguardando o Término da digitação...'
            this.recolherResposta()
        }
    },
    computed: {
        nomeFormatado() {
            console.log('executando cumputed')
            return this.nome.toUpperCase()
        },
        nomeFunction: {
            get: function () {
                console.log('executando function')
                return this.nome.toUpperCase()
            },
            set: function (novovalor) {
                this.nome = novovalor.substring(0,3)
            }
        }
    },
    methods: {
        recolherResposta() {
            let valor = this.busca
            setTimeout(() => {
                if (valor === this.busca) {
                    this.resultado = 'Terminou'
                }

            }, 5000)
        },
        calcula(sinal) {
            this.total = (sinal === '-') ? this.total - 1 : this.total + 1
        }
    }
}
</script>

<style>

</style>
