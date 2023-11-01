<script setup lang="ts">
import { ref } from 'vue'
import DarkModeToggle from "./darkmode/DarkModeToggle.vue";
const isDarkMode = ref(false);
const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
  document.body.classList.toggle('dark', isDarkMode.value);
};

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <div class="text-center text-xl">
    <h1 class="text-4xl leading-tight">{{ msg }}</h1>
    <div class="p-4">
      <div class="flex justify-center m-2 space-x-2">
        <button class="text-blue-500 rounded-xl border-2 border-blue-500 p-2" type="button" @click="count++">Count is {{ count }}</button>
        <DarkModeToggle @toggle-dark-mode="toggleDarkMode" :isDarkMode="isDarkMode"/>
      </div>
      <p>
        Edit <code>components/HelloWorld.vue</code> to test HMR
      </p>
    </div>
    <p>
      Install
      <a class="font-semibold text-[#646cff] hover:text-[#535bf2] duration-300 ease-in-out" href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
      in your IDE for a better DX
    </p>
    <p class="text-gray-400 dark:text-gray-700">Click on the Vite and Vue logos to learn more</p>
  </div>
</template>
