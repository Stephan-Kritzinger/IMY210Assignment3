<template>
    <div class="nav-element">
        <img :src="imgSrc" width="32" height="32"><span>{{ title }}</span>
    </div>
</template>

<script setup>
    defineProps({
        title: String,
        imgSrc: String
    })
</script>
<style scoped>
    @import './../styles/nav-element.css';
</style>