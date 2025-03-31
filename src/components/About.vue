<script setup>
import TrackArtWhite from "@/assets/track_art_white.png"
</script>

<template>
  <div class="w-full flex flex-col items-center bg-white dark:bg-black mb-12">
    <div class="mx-12 my-4 text-div">
      Invictus Athletics Club is an elite track and field club operating out of the Waterloo Region in Ontario. We focus
      on hurdles and sprints.
    </div>

    <div class="mx-12 my-4 text-div">
      Invictus AC was formed in 2016 by Head Coach Ray who has been coaching track and field in the region since the
      early 2000’s. Supported by his assistants over the years, many of whom are former athletes of Ray’s, Invictus has
      seen much success since being formed in the latter half of the 2010’s.
    </div>

    <img class="h-18 w-52" :src="TrackArtWhite" alt="Image of a Track"/>

    <div class="mx-12 my-4 text-div">
      As a club we aim to provide the highest quality of sprint and hurdle training to youth in the region
      who are at all levels of skill, and are at different points in their track and field careers. Our results and the
      places they take our athletes are a testament to the work we do.
    </div>

    <div class="mx-12 my-4 text-div">
      Ray has coached countless athletes throughout their elementary and high school years. Himself and the club have
      been instrumental in helping athletes achieve their goals and dreams on the track no matter how big or small. We
      form connections that last a lifetime and teach young people skills that translate to success in all areas of
      life.
    </div>
  </div>
</template>

<style scoped>
text-div {
  @apply text-black dark:text-white;
  font-family: "Fjalla One", sans-serif;
}
</style>