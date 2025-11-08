<template>
  <div>
    <input v-model="id" />
    <input v-model="password" type="password" />
    <p>{{ message }}</p>
    <button @click="whoami">whoami</button>
  </div>
</template>

<script>
export default { name: 'E03Binding' }
</script>

<script setup>
import { ref } from 'vue'

const message  = ref('Hello Vue')
const id       = ref('')
const password = ref('')

function whoami() {
  message.value = `${id.value} ${password.value}`
}
</script>

<style scoped>
/* 필요하면 스타일 추가 */
</style>