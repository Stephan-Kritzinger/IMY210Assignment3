<template>
    <div class="navbar">
        <NuxtLink to="/" ><navElement :title="'Home'" :img-src="'/img/home.svg'" /></NuxtLink>
        <NuxtLink to="/project" ><navElement :title="'Projects'" :img-src="'/img/folder.svg'" /></NuxtLink>
        <NuxtLink to="/contact" ><navElement :title="'Contact'" :img-src="'/img/phone-call.svg'" /></NuxtLink>
    </div>
</template>

<script setup>
    import navElement from './nav-element.vue';
</script>
<style scoped>
    @import './../styles/navbar.css';
</style>