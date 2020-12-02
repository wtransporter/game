<template>
    <section>
        <slot></slot>
    </section>    
</template>

<style scoped>
    section {
        border: 1px solid rgba(0, 0, 0, 0.26);
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
        border-radius: 5px;
        max-width: 640px;
        margin: 20px auto;
        padding: 0 5px 0 5px;
    }
</style>