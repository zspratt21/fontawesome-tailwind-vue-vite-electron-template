<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import DarkModeHandler from "./components/darkmode/DarkModeHandler.vue";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { library } from "@fortawesome/fontawesome-svg-core";
import { faFontAwesomeFlag } from "@fortawesome/free-brands-svg-icons";
library.add(faFontAwesomeFlag);

window.electronAPI.sendMessage('Hello from App.vue!');
</script>

<template>
  <DarkModeHandler class="bg-gray-100 dark:bg-gray-900 text-black dark:text-white min-h-screen font-sans">
    <div class="flex justify-center">
      <a href="https://fontawesome.com" target="_blank" class="duration-300 ease-in-out will-change-contents">
        <font-awesome-icon :icon="['fab', 'font-awesome-flag']" class="h-36 p-4 text-[#528DD7] hover:drop-shadow-[0_0_2em_#528DD7]"/>
      </a>
      <a href="https://tailwindcss.com" target="_blank" class="duration-300 ease-in-out will-change-contents">
        <img src="/tailwind.svg" class="h-36 p-4 hover:drop-shadow-[0_0_2em_#38BDF8]" alt="Tailwind logo" />
      </a>
      <a href="https://vitejs.dev" target="_blank" class="duration-300 ease-in-out will-change-contents">
        <img src="/vite.svg" class="h-36 p-4 hover:drop-shadow-[0_0_2em_#646cffaa]" alt="Vite logo" />
      </a>
      <a href="https://vuejs.org" target="_blank" class="duration-300 ease-in-out will-change-contents">
        <img src="/vue.svg" class="h-36 p-4 hover:drop-shadow-[0_0_2em_#42b883aa]" alt="Vue logo" />
      </a>
    </div>
    <HelloWorld msg="FontAwesome + Tailwind + Vite + Vue"/>
  </DarkModeHandler>
</template>
