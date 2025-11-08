<template>
  <div>
    <p>{{ message }}</p>
    <button @click="onSend">Send Event (1)</button>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ChildComponent1',
  props: { message: { type: String, required: true } },
  emits: ['custom-event'],
  setup(props, { emit }) {
    const onSend = () => emit('custom-event', 'Hello from child 1')
    // 템플릿에서 message를 쓰려면 반환 필요
    return { ...props, onSend }
  }
})
</script>

<style scoped>
/* 필요시 스타일 */
</style>