<template>
    <div>
        <label :for="searchLabel">{{ searchLabel }}</label>
        <input v-model="searchText" :name="searchLabel" :placeholder="'Search by ' + searchLabel">
    </div>
</template>

<script setup>
    const props = defineProps({
        searchLabel: String
    });

    const searchText = defineModel();
</script>

<style scoped>
    @import "/styles/search-bar.css";
</style>