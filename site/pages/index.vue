<template>
    <div id="category-dropdown">
        <div>Filter by category</div>
        <div @click="showDropdown" class="dropdown">
            <span ref="filter">--Select a Category--</span>
            <div ref="options" class="dropdown-options hidden">
                <div ref="clear" @click="filterDrop('clear')" class="hidden">Clear Filter</div>
                <div @click="filterDrop('Technology')">Technology</div>
                <div @click="filterDrop('Electronics')">Electronics</div>
            </div>
        </div>
    </div>
    <div v-if="blogs.length">
        <blog :ref="el => blogList[i] = el" v-for="(blog, i) in blogs" :key="i" :author="blog.author" :title="blog.title" :content="blog.content" :category="blog.category" />
    </div>
</template>

<script setup>
    import blog from "@/components/blog-blurb.vue";
    import {ref, onMounted} from "vue";

    const blogs = ref([
        {author: "e", title: "b", content: "e", category: "Technology"},
        {author: "a", title: "b", content: "e", category: "Electronics"},
        {author: "e", title: "c", content: "e", category: "Electronics"},
        {author: "a", title: "c", content: "e", category: "Electronics"}
    ])

    const options = ref(null);
    const filter = ref(null);
    const clear = ref(null);
    const blogList = ref([]);
    const route = useRoute();

    onMounted(async () => {
        if(route.query.author){
            blogs.value = blogs.value.filter(blogTemp => blogTemp.author === route.query.author);
        }
        if(route.query.blogTitle){
            blogs.value = blogs.value.filter(blogTemp => blogTemp.title === route.query.blogTitle);
        }
    });

    function showDropdown(){
        options.value.classList.toggle("hidden");
    }
    function filterDrop(filterVal){
        if(filterVal == 'clear'){
            filter.value.textContent = "--Select a Category--";
            clear.value.classList.add("hidden");
            blogList.value.forEach(blog => {
                blog.$el.classList.remove("hidden");
            });
        }
        else{
            filter.value.textContent = filterVal;
            clear.value.classList.remove("hidden");
            blogList.value.forEach(blog => {
                console.log(blogList.value);
                if(blog.$el.classList.contains(filterVal)){
                    blog.$el.classList.remove("hidden");
                }
                else{
                    blog.$el.classList.add("hidden");
                }
            });
        }
    }
</script>

<style scoped>
    @import "/styles/category.css";
    @import "/styles/dropdown.css";
</style>