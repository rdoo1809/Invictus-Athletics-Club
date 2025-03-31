<script setup>
import HeaderVideo from "@/assets/track.mp4"
</script>

<template>
  <div class="bg-white">
    <video class="background-video" autoplay loop muted playsinline>
      <source :src="HeaderVideo" type="video/mp4">
    </video>
    <div class="absolute inset-0 bg-black/40 mix-blend-overlay"></div>
  </div>
</template>

<style>

.background-video {
  object-fit: cover;
  height: 60vh;
  width: 100vw;
}
</style>