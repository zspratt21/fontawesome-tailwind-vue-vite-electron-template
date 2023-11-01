<template>
  <div :class="{ dark: isDarkMode }">
    <slot></slot>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const isDarkMode = ref(false);

    const toggleDarkMode = () => {
      isDarkMode.value = !isDarkMode.value;
      document.body.classList.toggle('dark', isDarkMode.value);
    };

    return { isDarkMode, toggleDarkMode };
  }
}
</script>