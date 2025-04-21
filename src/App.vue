<template>
  <div class="container">
    <div v-if="showMount">
      <LifeCycle></LifeCycle>
    </div>
    <div>
      <button @click.prevent="toggleMount">Toggle mount</button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import LifeCycle from './components/LifeCycle.vue';

export default defineComponent({
  components: {
    LifeCycle,
  },
  setup() {
    const showMount = ref(true);

    function toggleMount(): void {
      showMount.value = !showMount.value;
    }

    return {
      showMount,
      toggleMount,
    };
  },
});
</script>

<style>

body {
  height: 100%;
  margin: 100px;
  padding: 0;
  background-color: #fdf6ec;
}


.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 75vh;
  text-align: center;
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
  margin-top: 20px;
}

button:hover {
  background-color: #45a049;
}

</style>
