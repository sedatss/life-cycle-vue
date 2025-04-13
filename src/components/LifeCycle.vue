<template>
  <div class="container">
    <h1>Lifecycle Demo</h1>
    <p>Count: {{ count }}</p>
    <button @click="increment">Increment</button>
  </div>
</template>

<script lang="ts" setup>
import { ref, onMounted, onBeforeUpdate, onUpdated, onUnmounted, onBeforeMount, onBeforeUnmount } from 'vue'

const count = ref<number>(0)

function increment(): void {
  count.value++
}

onBeforeMount(() => {
  console.log('before Mount')
})

onMounted(() => {
  console.log('Component mounted')
})

onBeforeUpdate(() => {
  console.log('Before update (count =', count.value, ')')
})

onUpdated(() => {
  console.log('Component updated (count =', count.value, ')')
})

onBeforeUnmount(() => {
  console.log('beforeUnmount')
})

onUnmounted(() => {
  console.log('Component unmounted')
})
</script>

<style scoped>

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 50vh;
  text-align: center;
}

h1 {
  font-size: 3rem;
  color: #4CAF50;
  margin-bottom: 20px;
}

p {
  font-size: 1.25rem;
  margin: 10px 0;
}

button {
  padding: 10px 20px;
  font-size: 1rem;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #45a049;
}

</style>
