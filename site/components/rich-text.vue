<template>
    <div class="rich">
            <vue-markdown-render :source="content" />
        </div>
</template>

<script setup>
     import { ref } from "vue";
    import VueMarkdownRender from "vue-markdown-render";

    const props = defineProps({
        text: String
    });

    const content = ref(props.text);
</script>