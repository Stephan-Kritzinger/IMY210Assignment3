<template>
    <div class="media">
        <img :src="imgUrl" width="300" height="256">
    </div>
</template>

<script setup>
    import {ref, onMounted} from "vue";

    const props = defineProps({
        id: Number
    })
    const imgUrl = ref();
    onMounted(async () => {
        const response = await fetch(`http://localhost:1337/api/upload/files/${props.id}`);
        const data = await response.json();
        imgUrl.value = `http://localhost:1337${data.url}`;
    });
</script>