<template>
    <article>
        <h2>{{ titulo }}</h2>
        <p v-html="conteudo"></p>
    </article>
</template>

<script>
export default {
    name: "LvCards",
    props: ["titulo", "conteudo"]
}
</script>

<style scoped>
    article {
        width: fit-content;
        border: 1px solid #000;
        border-radius: 30px;
        padding: 0 20px;
    }
</style>