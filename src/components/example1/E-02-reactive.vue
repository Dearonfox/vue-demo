<template>
  <div>{{ fullName }}</div>
</template>

<script>
export default { name: 'E02Reactive' }
</script>

<script setup>
import { ref, computed, onMounted } from 'vue'

const firstName = ref('Kyungsu')
const lastName  = ref('123')

const fullName = computed(() => `${firstName.value} ${lastName.value}`)

onMounted(() => {
  console.log('mount')
  setTimeout(() => {
    firstName.value = 'KSL'
  }, 2000)
})
</script>

<style scoped>
/* 필요하면 스타일 추가 */
</style>