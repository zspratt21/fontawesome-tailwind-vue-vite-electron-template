<template>
  <button @click="toggleDarkMode" class="rounded-full w-12 h-12 bg-gray-200 dark:bg-gray-800 p-2">
    <font-awesome-icon :icon="['fas', isDarkMode ? 'sun' : 'moon']" />
  </button>
</template>

<script>
import {FontAwesomeIcon} from "@fortawesome/vue-fontawesome";
import {library} from "@fortawesome/fontawesome-svg-core";
import {faMoon, faSun} from "@fortawesome/free-solid-svg-icons";
library.add(faMoon);
library.add(faSun)
export default {
  props: ['isDarkMode'],
  components: {FontAwesomeIcon},
  methods: {
    toggleDarkMode() {
      this.$emit('toggle-dark-mode');
    }
  }
}
</script>