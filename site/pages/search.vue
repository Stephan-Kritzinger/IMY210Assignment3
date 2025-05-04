<template>
    <div>
        <searchbar :search-label="'Author'" />
    </div>
    <div>Or</div>
    <div>
        <searchbar :search-label="'Blog Title'" />
    </div>
</template>

<script setup>
    import searchbar from "@/components/search-bar.vue";
</script>