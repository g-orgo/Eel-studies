<script setup lang="ts">
import { ref } from "vue";

const number = ref<number>(0);
const ping = ref<boolean>(false);

const click = () => {
  number.value++;
  ping.value = true;

  setTimeout(() => {
    ping.value = false;
  }, 500);
};
</script>

<template>
  <div class="w-screen h-screen flex items-center justify-center">
    <div class="flex flex-col items-center rounded-full p-20">
      <img
        :class="{ 'animate-ping': ping }"
        class="w-10 h-10"
        src="./assets/vue.svg"
      />
      <h1>{{ number }}</h1>
      <button class="py-2 px-4 rounded border" @click="click">Clica?!</button>
    </div>
  </div>
</template>
