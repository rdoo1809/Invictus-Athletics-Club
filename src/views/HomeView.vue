<script setup>
import NavBar from "@/components/NavBar.vue";
import ThemeToggler from "@/components/ThemeToggler.vue";
import {watch} from "vue";
import {useDark} from "@vueuse/core";
import Footer from "@/components/Footer.vue";
import MediaScroller from "@/components/MediaScroller.vue";
import About from "@/components/About.vue";
import VideoHeader from "@/components/VideoHeader.vue";

const isDark = useDark();

watch(isDark, (newVal) => {
  console.log("Theme changed:", newVal);
});
</script>

<template>
  <NavBar/>
<!--  <VideoHeader />-->
  <MediaScroller />
<!--  <About />-->

  <Footer />
  <ThemeToggler/>
</template>



