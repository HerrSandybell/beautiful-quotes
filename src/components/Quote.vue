<template>
    <blockquote class="container blockquote">
        <slot></slot>
    </blockquote>
</template>

<script>
    export default {
        data() {
            return {
                quoteLimit: 10,
                quotes: ["Test"]
            }
        }
    }
</script>

<style scoped>
    .container {
        border: 1px solid gray;
        width: 30%;
        font-family: Arizonia;
        font-size: 2rem;
        border-radius: 5px;
    }

    blockquote:hover {
        background: rgb(231, 171, 171);
    }
</style>
