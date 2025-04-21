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

onBeforeMount(function (): void {
  console.log('before Mount');
});

onMounted(function (): void {
  console.log('Component mounted');
});

onBeforeUpdate(function (): void {
  console.log('Before update (count =', count.value, ')');
});

onUpdated(function (): void {
  console.log('Component updated (count =', count.value, ')');
});

onBeforeUnmount(function (): void {
  console.log('beforeUnmount');
});

onUnmounted(function (): void {
  console.log('Component unmounted');
});

function increment(): void {
  count.value++
}

</script>

<style scoped>

.container {
  width: 100%;
  max-width: 500px;
  padding: 2.5rem;
  border-radius: 16px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  box-sizing: border-box;
  border: 1px solid #ddd;
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
