<template>
    <h3>Buscando rivais</h3>
    <label>Time:
        <input v-model="busca" type="text">
        <p>Rival: {{ rival(busca) }}</p>
    </label>
</template>

<script>
export default {
    name: "BuscaTime",
    data() {
        return {
            busca: ""
        }
    },
    methods: {
        rival(time) {
            switch (time.toLowerCase()) {
                case 'corinthians':
                    return 'palmeiras'
                case 'santos':
                    return 'são paulo'
                case 'flamengo':
                    return 'vasco'
                default:
                    return 'não encontrado'

            }
        }
    }
}
</script>

<style scoped>

</style>