<template>
    <h1 v-once v-text="titulo"></h1>
    <h2>{{ subtitulo }}</h2>

    <input type="text" v-bind:disabled="tarefas.length === 0" v-model="subtitulo" placeholder="Descrição">

<!--    pode substituir o termo v-bind usando apenas o : -->
<!--    <input type="text" :disabled="tarefas.length === 0" v-model="subtitulo" placeholder="Descrição">-->

    <div v-if="tarefas.length <= 0">
        Não há tarefas
    </div>
    <div v-if="tarefas.length > 0">
        Existem {{ tarefas.length }} tarefas

        <ul>
            <li v-for="(tarefa, id) in tarefas" :key="id">{{ tarefa }}</li>
        </ul>
    </div>

    <button v-on:click="tarefas = []">Limpar</button>

<!--    pode substituir o termo v-on: usando apenas o @ -->
<!--    <button @click="tarefas = []">Limpar</button>-->
    <hr>

    <p v-text="nome"></p>
    <br>
    <small v-once >{{ nome }}</small>

    <button v-bind:disabled="nome === 'Mané Garrincha'" v-if="nome !== ''" v-on:click="nome = ''">Apagar</button>

    <button v-if="nome === ''" v-on:click="nome = 'Mané Garrincha'">Mostrar</button>
    <br>
    <input v-model="nome" type="text">

    <ul>
        <li v-for="(cadeira, id) in cadeiras" :key="id">{{ cadeira }}</li>
    </ul>
</template>

<script>
export default {
    name: 'lv-tarefas',
    data() {
        return {
            titulo: 'Listagem de tarefas',
            subtitulo: 'Defina uma descrição',
            nome: 'Mané Garrincha',
            cadeiras: ["30","20","10"],
            tarefas: []
        }
    },
    mounted() {
        setInterval(() => {
            this.titulo = "Novo"
            this.tarefas = ["Acordar cedo", "Ir trabalhar"]
            this.nome = "Mineirão"
        }, 2000);

    }
}
</script>

<style>

</style>
