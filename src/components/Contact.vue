<script setup>
import TrackArt from "@/assets/track_art.webp";
</script>

<template>
  <div id="contact" class="w-full flex justify-center bg-white dark:bg-black py-12">
    <div class="sub-container w-3/4 my-4 flex flex-col items-center gap-4">
      <h2>GET IN TOUCH WITH US!</h2>
      <h2 class="w-full">We would love to hear about you and your Track and Field goals!</h2>
      <img class="h-24" :src="TrackArt" alt="Image of a Track"/>
      <h2><a href="mailto:info@invictusathletics.ca?subject=Invictus Athletics Club - Website Contact">Click to CONTACT</a></h2>
    </div>
  </div>
</template>

<style scoped>
.sub-container {
  background-color: rgba(255, 215, 0, 0.8);
  border-radius: 32px;
  padding: 24px;
}

a {
  text-decoration: underline;
  text-decoration-color: whitesmoke;
}

h2 {
  font-family: "Fjalla One", sans-serif;
  font-size: 24px;
}

@media screen and (min-width: 500px) {
  .sub-container {
    padding: 12px;
  }
}
</style>