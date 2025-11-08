<template>
  <div>
    <h2>{{ title }}</h2>
    <p>Full Name: {{ fullName }}</p>
    <input v-model="firstName" placeholder="First Name" />
    <input v-model="lastName" placeholder="Last Name" />
    <button @click="greet">Greet</button>
    <p>Greeting Count: {{ greetCount }}</p>
    <p>{{ message }}</p>
  </div>
</template>

<script>
import {
  defineComponent,
  ref,
  computed,
  watch,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
} from 'vue'

export default defineComponent({
  name: 'E07OptionsApi',
  props: {
    title: {
      type: String,
      default: 'User Information',
    },
  },
  setup(props) {
    // beforeCreate / created 대체 (로그 유지용)
    console.log('beforeCreate hook')
    console.log('created hook')

    // state (data -> ref)
    const firstName = ref('John')
    const lastName = ref('Doe')
    const greetCount = ref(0)
    const message = ref('')

    // computed
    const fullName = computed(() => `${firstName.value} ${lastName.value}`)

    // methods
    const greet = () => {
      greetCount.value++
      message.value = `Hello, ${fullName.value}!`
    }
    const resetGreetCount = () => {
      greetCount.value = 0
    }

    // watch
    watch(greetCount, (newValue, oldValue) => {
      console.log(`Greet count changed from ${oldValue} to ${newValue}`)
      if (newValue >= 3) {
        message.value = "That's enough greetings for now!"
      }
    })

    // lifecycle
    onBeforeMount(() => console.log('beforeMount hook'))
    onMounted(() => console.log('mounted hook'))
    onBeforeUpdate(() => console.log('beforeUpdate hook'))
    onUpdated(() => console.log('updated hook'))
    onBeforeUnmount(() => console.log('beforeUnmount hook'))
    onUnmounted(() => console.log('unmounted hook'))

    // 템플릿에서 쓰는 것만 반환
    return {
      // props는 템플릿에서 직접 접근 가능하지만 명시적으로는 반환 X
      firstName,
      lastName,
      greetCount,
      message,
      fullName,
      greet,
      resetGreetCount,
    }
  },
})
</script>