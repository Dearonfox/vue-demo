<template>
  <div>
    <p>{{ message }}</p>
    <button @click="onSend">Send Event (2)</button>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ChildComponent2',
  props: { message: { type: String, required: true } },
  emits: ['custom-event'],
  setup(props, { emit }) {
    const onSend = () => emit('custom-event', 'Hello from child 2')
    return { ...props, onSend }
  }
})
</script>

<style scoped>
/* 필요시 스타일 */
</style>