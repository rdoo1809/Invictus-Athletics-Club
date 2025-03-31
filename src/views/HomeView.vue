<script setup>
import NavBar from "@/components/NavBar.vue";
import ThemeToggler from "@/components/ThemeToggler.vue";
import {watch} from "vue";
import {useDark} from "@vueuse/core";

const isDark = useDark();

watch(isDark, (newVal) => {
  console.log("Theme changed:", newVal);
});
</script>

<template>
  <NavBar/>

  <div class="max-w-full flex justify-center">

    <div class="max-w-7xl flex items-start justify-center shadow-md p-6 rounded-md bg-white dark:bg-black mt-20">

      <div class="flex flex-col sm:items-center mb-4">
        <h1 class="text-4xl dark:text-white">
          Vue + Vite + Tailwind Dark/Light Mode Toggler
        </h1>
        <p class="dark:text-white my-4">This is a template application to be used as a starting point for a new front end.</p>
        <p class="dark:text-white">Comes equipped with a manual light/dark mode toggle switch, and hamburger nav for mobile display.</p>
      </div>
    </div>

  </div>

  <ThemeToggler/>
</template>



