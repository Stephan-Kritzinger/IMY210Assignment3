<template>
    <div class="quote">
        `<span id="message">{{ message }}</span>` - {{ author }}
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