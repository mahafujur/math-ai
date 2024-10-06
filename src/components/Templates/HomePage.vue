<script lang="ts" setup>

import {ref} from "vue";

const count = ref<number>(0)

const increment = () => {
  return count.value++;
}
const decrement = () => {
  return count.value-- ;
  // data(){
  //  return {
  //    count: 0;
  //  }
}
const reset = () => {
  count.value = 0;
};
</script>

<template>
  <div class="counter">
    <h1>Counter: {{ count }}</h1>
    <button @click="increment">Increase To {{count+1}}</button>
    <button v-if="count>0" :disabled="count<1" @click="decrement">Decrease To {{count-1}}</button>
  </div>
</template>

<style scoped>
.counter {
  text-align: center;
  margin-top: 50px;
}

button {
  margin: 5px;
  padding: 10px 20px;
  background-color: #42b983;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #333;
}
button:disabled {
  background-color: gray;
}
</style>
