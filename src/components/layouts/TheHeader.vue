<template>
    <header>
        <h3>{{ title }}</h3>
    </header>
</template>

<script>
    export default {
        props: ['title'],
    }
</script>

<style scoped>
    header {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 80px;
        background-color: #007791;
    }
    header h3 {
        margin: 0;
        font-size: 32px;
        color: white;
    }
</style>
