<script setup>
import HeaderVideo from "@/assets/track.mp4"
</script>

<template class="relative h-full">
  <div>
    <video class="background-video" autoplay loop muted playsinline>
      <source :src="HeaderVideo" type="video/mp4">
    </video>
<!--    <div class="absolute inset-0 bg-black/40 mix-blend-overlay overlay-height"></div>-->
  </div>
</template>

<style>

.background-video {
  object-fit: cover;
  height: 60vh;
  width: 100vw;
}

.overlay-height {
  height: 82vh;
}
</style>