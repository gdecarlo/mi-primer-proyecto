<template>
    <h2 class="nombre">{{ nombre }}</h2>
</template>

<script setup>
defineProps({
    nombre: String
})
</script>

<style scoped>
.nombre{
    color: blueviolet;
}
</style>