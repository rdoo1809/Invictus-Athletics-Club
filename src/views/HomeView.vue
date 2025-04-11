<script setup>
import NavBar from "@/components/NavBar.vue";
import ThemeToggler from "@/components/ThemeToggler.vue";
import {watch} from "vue";
import {useDark} from "@vueuse/core";
import Footer from "@/components/Footer.vue";
import MediaScroller from "@/components/MediaScroller.vue";
import About from "@/components/About.vue";
import VideoHeader from "@/components/VideoHeader.vue";
import Contact from "@/components/Contact.vue";

const isDark = useDark();

watch(isDark, (newVal) => {
  console.log("Theme changed:", newVal);
});
</script>

<template>
  <NavBar/>

  <div class="flex justify-center p-10 bg-white dark:bg-black">
    <h1 class="text-6xl font-bold text-black dark:text-white">INVICTUS</h1>
  </div>

  <VideoHeader />

  <MediaScroller />

  <About/>

  <Contact />

  <Footer />

  <ThemeToggler/>
</template>

<style>
  h1 {
    font-family: "Fjalla One", sans-serif;
  }
</style>


