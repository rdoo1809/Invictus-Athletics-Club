<script setup>
import {ref} from "vue";
import LogoBlack from "@/assets/logo_black.webp"
import LogoWhite from "@/assets/logo_white.webp"
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
        <a href="#gallery" class="nav-link">GALLERY</a>
        <a href="#about" class="nav-link">ABOUT</a>
        <a href="#contact" class="nav-link">CONTACT</a>
      </div>

      <!-- Mobile Nav -->
      <div class="md:hidden">
        <button @click="toggleMenu" class="text-black dark:text-white focus:outline-none text-2xl">
          ☰
        </button>
      </div>
    </div>

    <div v-if="isOpen" class="md:hidden bg-white dark:bg-black">
      <a href="#" class="nav-link mobile">ABOUT</a>
      <a href="#" class="nav-link mobile">HISTORY</a>
      <a href="#" class="nav-link mobile">GALLERY</a>
      <a href="#" class="nav-link mobile">CONTACT</a>
    </div>
  </nav>
</template>

<style scoped>
.nav-link {
  @apply text-black dark:text-white hover:text-yellow-400 dark:hover:text-yellow-400 text-lg;
  font-family: "Fjalla One", sans-serif;
}

.mobile {
  @apply block px-4 py-2
}
</style>