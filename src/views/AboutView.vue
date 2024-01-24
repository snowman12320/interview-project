<script>
import { useCounterStore } from '@/stores/counter.js';

export default {
  setup() {
    const counterStore = useCounterStore();
    return {
      counterStore,
    };
  },
  data() {
    return {
      title: 'About',
    };
  },
  methods: {
    toggleTitle() {
      this.title = this.title === 'About' ? 'About Vue' : 'About';
    },
  },
};
</script>

<template>
  <div class="about">
    <h1>
      This is an {{ title }} page
      <button @click="toggleTitle">Toggle title</button>
    </h1>
    <div class="counter-wrap">
      <button @click="counterStore.decrement">-</button>
      <p>Counter: {{ counterStore.counter }}</p>
      <p>doubleCount: {{ counterStore.doubleCount }}</p>
      <button @click="counterStore.increment">+</button>
    </div>
  </div>
</template>

<style>
.counter-wrap {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
}

@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    row-gap: 2rem;
  }
}
</style>
