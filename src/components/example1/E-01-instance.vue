<template>
  <div>Hello, {{ message }}</div>
</template>

<script>
export default { name: 'E01Instance' }
</script>

<script setup>
import { ref } from 'vue'
const message = ref('Vue!')
</script>

<style scoped>
div { color: blue; }
</style>