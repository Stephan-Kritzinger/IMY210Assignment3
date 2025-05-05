<template>
    <div class="quote">
        `<span id="message">{{ message }}</span>` - <span id="author">{{ author }}</span>
    </div>
</template>

<script setup>
    import { ref } from "vue";

    const props = defineProps({
        message: String,
        author: String
    });

    const message = ref(props.message);
    const author = ref(props.author);
</script>

<style scoped>
    @import "/styles/quote.css";
</style>