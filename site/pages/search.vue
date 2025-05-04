<template>
    <searchbar v-model="author" :search-label="'Author'" />
    <div>And</div>
    <searchbar v-model="blogTitle" :search-label="'Blog Title'" />
    <div id="button">
        <button @click="search">Search</button>
    </div>
</template>

<script setup>
    import { useRouter } from 'nuxt/app';

    import searchbar from "@/components/search-bar.vue";
    const author = ref('');
    const blogTitle = ref('');
    function search(){
        

        const searchTerm = {};
        if(author.value != ''){
            searchTerm.author = author.value;
        }
        if(blogTitle.value != ''){
            searchTerm.blogTitle = blogTitle.value;
        }

        const router = useRouter();
        router.push({path: '/', query: searchTerm});

    }
</script>

<style scoped>
    @import "/styles/search.css";
</style>