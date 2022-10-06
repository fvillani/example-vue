<template>
    <ul>
        <li v-for="(item, id) in listaFormatada" :key="id">{{ item }}</li>
    </ul>
</template>

<script>
export default {
    name: "LvLista2",
    props: {
        ordena: null,
        lista: {
            require: true,
            type: Array,
            default () {
                return []
            }
        }
    },
    computed: {
        listaFormatada() {
            if (typeof this.ordena != 'undefined') {
                return new Array(...this.lista).sort()
            }

            return this.lista
        }
    }
}
</script>

<style scoped>

</style>