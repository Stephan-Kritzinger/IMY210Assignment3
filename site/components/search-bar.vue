<template>
    <label :for="searchLabel">{{ searchLabel }}</label>
    <input :name="searchLabel">
</template>

<script setup>
    const props = defineProps({
        searchLabel: String
    })
</script>

<style scoped>
    @import "/styles/search-bar.css";
</style>