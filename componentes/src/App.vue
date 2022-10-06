<template>
    <BuscaTime />
    <hr>
    <PerfilTime />
</template>

<script>
import BuscaTime from "@/components/BuscaTime";
import PerfilTime from "@/components/PerfilTime";

export default {
    name: 'App',
    components: {
        BuscaTime,
        PerfilTime
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
