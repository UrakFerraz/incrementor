<template>
  <section class="container">
    <input type="number" placeholder="0" v-model="counter" />
    <div class="btnsWrapper">
      <button @click.prevent="reset">Reset</button>
      <button @click.prevent="increment">Increment</button>
      <button @click.prevent="decrement">Decrement</button>
    </div>
  </section>
</template>

<script>
import { ref } from 'vue';
export default {
  setup() {
    let counter = ref(0);
    function increment() {
      counter.value++;
    }
    function decrement() {
      counter.value--;
    }
    function reset() {
      counter.value = 0;
    }
    return {
      counter,
      increment,
      decrement,
      reset,
    };
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Big+Shoulders+Text:wght@100;200;300;400;500;600;700;800;900&display=swap');
* {
  box-sizing: border-box;
  font-family: 'Big Shoulders Text', cursive;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
  display: flex;
  align-content: center;
  justify-content: center;
  background: rgb(13, 9, 36);
}

.container {
  background: white;
  padding: 1rem;
  text-align: center;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 1fr 4fr;
  gap: 10px;
  width: 100vw;
  height: 100vh;
}

.btnsWrapper {
  display: grid;
  gap: 10px;
  grid-template-columns: 1fr;
  grid-template-rows: auto repeat(2, 1fr);
}

input {
  border: none;
  outline: none;
  text-align: center;
  font-size: 11vh;
  width: 100%;
}

.btnsWrapper button:nth-child(1) {
  align-self: center;
  justify-self: center;
  font-size: 16px;
}

.btnsWrapper button {
  outline: none;
  border: none;
  border-radius: 6px;
  font-size: 5vh;
  padding: 10px;
}

.btnsWrapper button:hover {
  background: rgba(0, 0, 0, 0.26);
}
</style>