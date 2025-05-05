<template>
    <div id = "title">{{  title }}</div>
    <div id = "category">{{ category }}</div>
    <div id="author">{{ author }}</div>
    <div id="body">
        <component v-for="(block, i) in blocks" :key="i" :is="getComponent(block.__component)" v-bind="getProps(block)" />
    </div>
</template>

<script setup>
   import {ref, onMounted} from "vue";
   import richText from "@/components/rich-text.vue";
   import quote from "@/components/quote.vue";
   import media from "@/components/media.vue";
   import slider from "@/components/slider.vue";

   const page = ref();
   const title = ref("");
   const author = ref("");
   const category = ref("");
   const blocks = ref([]);

   const parseData = async() => {
        const response = await fetch("http://localhost:1337/api/articles/imouhuv8w93ylge0506g7goc?populate[0]=author&populate[1]=category&populate[2]=blocks&populate[3]=blocks.files");
        const data = await response.json();
        page.value = data.data;
   }

   onMounted(async () => {
    await parseData();
    title.value = page.value.title;
    author.value = page.value.author.name;
    category.value = page.value.category.name;
    blocks.value = page.value.blocks;
   });

   const getComponent = (type) => {
    const componentMap = {
        "shared.rich-text": richText,
        "shared.quote": quote,
        "shared.media": media,
        "shared.slider": slider
    }
    return componentMap[type] || "div";
   }

   const getProps = (block) => {
    switch(block.__component){
        case "shared.rich-text":
            return {text: block.body};
        case "shared.quote":
            return {message: block.body, author: block.title};
        case "shared.media":
            return {id: block.id};
        case "shared.slider":
            return {imageIds: block.files.map(file => file.id) };
    }
   }
</script>