<template>
    <h4>Lista</h4>
    <LvLista :lista="['feijão', 'arroz', 'carne']" />

    <br />
    <h4>Lista Ordenada</h4>
    <LvLista :lista="['feijão', 'arroz', 'carne']" :ordena="true" />

    <br />
    <h4>Lista Ordenada 2</h4>
    <LvLista2 :lista="['feijão', 'arroz', 'carne']" :ordena="true" />

    <br />
    <LvCards :titulo="'Preço'" :conteudo="'Tudo <strong>Barato</strong>'" />

    <LvCards2 :titulo="'Preço 2'">
        <p>Tudo <strong>Barato 2</strong></p>

        <template v-slot:rodape>
            <small>aproveite</small>
        </template>
    </LvCards2>

</template>

<script>
import LvLista from "@/components/LvLista";
import LvLista2 from "@/components/LvLista2";
import LvCards from "@/components/LvCards";
import LvCards2 from "@/components/LvCards2";

export default {
    name: 'App',
    components: {
        LvLista,
        LvLista2,
        LvCards,
        LvCards2
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
