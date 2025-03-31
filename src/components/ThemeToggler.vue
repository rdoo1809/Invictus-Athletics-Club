<script setup>
import {useDark, useToggle} from "@vueuse/core";
import Moon from "@/assets/moon-light.svg"
import Sun from "@/assets/sun-light.svg"

const isDark = useDark();
const toggleDark = useToggle(isDark);
</script>

<template>
  <div class="absolute bottom-0 right-0 m-4">
    <label class="relative inline-flex items-center cursor-pointer">
      <input type="checkbox" class="sr-only peer" @click="toggleDark()"/>

      <!-- Outer Pill -->
      <div
          class="w-24 h-12 bg-gray-400 dark:bg-gray-700 rounded-full transition-all flex items-center px-1">

        <!-- Inner Circle -->
        <div
            class="w-10 h-10 bg-white rounded-full border border-gray-300 flex items-center justify-center transition-all"
            :class="{'translate-x-[3rem]': isDark}">

          <img :src="isDark ? Sun : Moon" alt="Logo" class="w-6 h-6 select-none">

        </div>
      </div>
    </label>
  </div>
</template>