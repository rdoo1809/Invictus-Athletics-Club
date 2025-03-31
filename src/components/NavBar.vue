<script setup>
import {computed, ref, watch} from "vue";
import LogoBlack from "@/assets/logo_black.png"
import LogoWhite from "@/assets/logo_white.png"
import {useDark} from "@vueuse/core";

const isOpen = ref(false);
const isDark = useDark();

const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};
</script>

<template>
  <nav class="bg-white dark:bg-black shadow-md">
    <div class="h-24 px-4 flex justify-between items-center">

      <img :src="isDark ? LogoWhite : LogoBlack" alt="Logo" class="h-20 w-20">

      <div class="hidden md:flex space-x-6">
        <a href="#" class="nav-link">NavLink1</a>
        <a href="#" class="nav-link">NavLink2</a>
        <a href="#" class="nav-link">NavLink3</a>
        <a href="#" class="nav-link">NavLink4</a>
      </div>

      <!-- Mobile Nav -->
      <div class="md:hidden">
        <button @click="toggleMenu" class="text-black dark:text-white focus:outline-none text-2xl">
          ☰
        </button>
      </div>
    </div>

    <div v-if="isOpen" class="md:hidden bg-white dark:bg-black">
      <a href="#" class="nav-link-mobile">NavLink1</a>
      <a href="#" class="nav-link-mobile">NavLink2</a>
      <a href="#" class="nav-link-mobile">NavLink3</a>
      <a href="#" class="nav-link-mobile">NavLink4</a>
    </div>
  </nav>
</template>

<style scoped>
.nav-link {
  @apply text-black dark:text-white hover:text-blue-500;
}

.nav-link-mobile {
  @apply block px-4 py-2 text-black dark:text-white hover:bg-gray-200 dark:hover:bg-gray-400
}
</style>