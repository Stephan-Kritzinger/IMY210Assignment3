<template>
    <div class="blog" :class="category">
        <div id="author">
            {{ author }}
        </div>
        <div id="title">
            <NuxtLink :to="`/blog?docId=${id}`"> {{ title }} </NuxtLink>
        </div>
        <div id="content">
            {{ content }}
        </div>
    </div>
</template>

<style scoped>
    @import '/styles/blog-blurb.css';
</style>

<script setup>
    const props = defineProps({
        category: String,
        author: String,
        content: String,
        title: String,
        id: String
    });
</script>