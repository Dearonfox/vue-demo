<template>
  <div>
    <input ref="inputField" type="text" placeholder="Click the button to focus" />
    <button @click="focusInput">Focus Input</button>
  </div>
</template>

<script>
export default { name: 'E12RefComponent' }
</script>

<script setup>
import { ref, onMounted } from 'vue'

const inputField = ref(null) // DOM 요소 ref

const focusInput = () => {
  inputField.value && inputField.value.focus()
}

onMounted(() => {
  console.log(inputField)
  if (inputField.value) inputField.value.focus()
})
</script>