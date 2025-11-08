<template>
  <div>
    <ChildComponent
        :message="parentMessage"
        @custom-event="handleEvent"
    />
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import ChildComponent from './ChildComponent.vue'

export default defineComponent({
  name: 'E05ParentComponent',
  components: { ChildComponent }
})
</script>

<script setup>
import { ref } from 'vue'

const parentMessage = ref('Hello from parent')

function handleEvent(payload) {
  console.log(payload)
}
</script>