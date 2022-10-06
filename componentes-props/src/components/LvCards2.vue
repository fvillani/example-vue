<template>
    <article>
        <h2>{{ titulo }}</h2>
        <slot></slot>
        <hr />
        <slot name="rodape"></slot>
    </article>
</template>

<script>
export default {
    name: "LvCards2",
    props: ["titulo"]
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