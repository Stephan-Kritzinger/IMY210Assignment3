<template>
    <div class="slider">
        <media :id="currentImageId" :key="currentImageId"/>
        <button @click="prev">&lt; Prev</button>
        <button @click="next">Next &gt;</button>
    </div>
</template>

<script setup>
    import { ref, onMounted, onUnmounted, computed } from "vue";
    import media from "@/components/media.vue";

    const props = defineProps({
        imageIds: Array
    });

    const currentIndex = ref(0);
    const currentImageId = computed(() => props.imageIds[currentIndex.value]);
    let interval = null;

    const prev = () => {
        currentIndex.value = (currentIndex.value - 1 + props.imageIds.length) % props.imageIds.length;
    };

    const next = () => {
        currentIndex.value = (currentIndex.value + 1) % props.imageIds.length;
    };

    onMounted(() => {
        interval = setInterval(() => {
            next();
        }, 5000);
    })
    onUnmounted(() => {
        clearInterval(interval);
    })
</script>

<style scoped>
    @import "/styles/carousel.css";
</style>