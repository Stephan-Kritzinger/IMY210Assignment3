<template>
  <div>
    <div id="nav">
      <navbar />
    </div>
    <div id="body">
      <NuxtPage />
    </div>
  </div>
</template>

<script setup>
  import navbar from './components/navbar.vue';
</script>
