<template>
  <div>
    <p>{{ message }}</p>
    <button @click="onSend">Send Event</button>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ChildComponent',
  props: { message: { type: String, required: true } },
  emits: ['custom-event'],
  setup(props, { emit }) {
    const onSend = () => emit('custom-event', 'Hello from child')
    return { onSend, ...props }
  }
})
</script>