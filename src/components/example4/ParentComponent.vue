<template>
  <div>
    <ChildComponent1
        :message="parentMessage1"
        @custom-event="handleFromChild1"
    />

    <ChildComponent2
        :message="parentMessage2"
        @custom-event="handleFromChild2"
    />
  </div>
</template>

<script>
export default { name: 'E05ParentComponent' }
</script>

<script setup>
import { ref } from 'vue'
import ChildComponent1 from './ChildComponent1.vue'
import ChildComponent2 from './ChildComponent2.vue'

const parentMessage1 = ref('Hello from parent #1')
const parentMessage2 = ref('Hello from parent #2')

function handleFromChild1(payload) {
  console.log('Child1 says:', payload)
}
function handleFromChild2(payload) {
  console.log('Child2 says:', payload)
}
</script>

<style scoped>
/* 필요시 스타일 */
</style>