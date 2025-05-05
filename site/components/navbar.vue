<template>
    <div class="navbar">
        <NuxtLink to="/" ><navElement :title="'Home'" :img-src="'/img/home.svg'" /></NuxtLink>
        <NuxtLink to="/search" ><navElement :title="'Search'" :img-src="'/img/search.svg'" /></NuxtLink>
        <NuxtLink to="/blog" ><navElement :title="'Blog'" :img-src="'/img/phone-call.svg'" /></NuxtLink>
    </div>
</template>

<script setup>
    import navElement from './nav-element.vue';
</script>
<style scoped>
    @import './../styles/navbar.css';
</style>