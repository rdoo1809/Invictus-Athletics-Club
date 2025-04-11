<script setup>
import {onMounted, onUnmounted, ref} from 'vue';
import Image1 from "@/assets/scroller/aidenC.webp"
import Image2 from "@/assets/scroller/beechy.webp"
import Image3 from "@/assets/scroller/coleCoach.webp"
import Image4 from "@/assets/scroller/oliv.webp"
import Image5 from "@/assets/scroller/threeAmi.webp"
import Image6 from "@/assets/scroller/jusKay.webp"
import Image7 from "@/assets/scroller/districtC.webp"
import Image8 from "@/assets/scroller/alissaRay.webp"
import Image9 from "@/assets/scroller/girlRelay.webp"
import Image10 from "@/assets/scroller/squad2017.webp"
import Image11 from "@/assets/scroller/teamO.webp"
import Image12 from "@/assets/scroller/squad2018.webp"
import Image13 from "@/assets/scroller/girls_team.webp"
import Image14 from "@/assets/scroller/boys_team.webp"
import Image15 from "@/assets/scroller/bellBren.webp"
import Image16 from "@/assets/scroller/alum2019.webp"

const images = ref([
  Image1, Image5, Image13, Image14, Image4, Image3, Image2, Image6, Image7, Image8, Image9, Image15, Image16, Image10, Image11, Image12
]);

const selectedImage = ref(null);

const openFullImg = (pic) => {
  selectedImage.value = pic;
  console.log(selectedImage)
};

const closeFullImg = () => {
  selectedImage.value = null;
};

const handleKeyDown = (e) => {
  if (e.key === "Escape") closeFullImg();
};

onMounted(() => window.addEventListener("keydown", handleKeyDown));
onUnmounted(() => window.removeEventListener("keydown", handleKeyDown));
</script>

<template>
  <div id="gallery" class="media-scroller snaps-inline bg-white dark:bg-black pt-12">
    <div
        v-for="(img, index) in images"
        :key="index"
        class="media-element">
      <img :src="img" alt="Image" @click="openFullImg(img)" />
    </div>
  </div>

    <div class="w-full flex justify-end dark:bg-black">
      <p class="text-xs font-thin mr-2 my-2 dark:text-white">Click to Enlarge</p>
    </div>

  <div v-if="selectedImage" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-80 z-50">
    <div class="relative max-w-4xl w-full p-4">
      <button
          class="absolute top-2 right-2 text-white text-3xl"
          @click="closeFullImg">X</button>
      <img :src="selectedImage" class="w-full max-h-[80vh] object-contain rounded-md" />
    </div>
  </div>
</template>

<style scoped>
@import "https://unpkg.com/open-props";
@import "https://unpkg.com/open-props/normalize.min.css";

.media-scroller {
  display: grid;
  gap: var(--_spacer);
  grid-auto-flow: column;
  grid-auto-columns: 21%;
  padding: 0 var(--_spacer) var(--_spacer);
  overflow-x: auto;
  overscroll-behavior-inline: contain;
  scrollbar-color: gold saddlebrown;
}

.media-scroller::-webkit-scrollbar {
  width: 0.5px;
}

.media-scroller::-webkit-scrollbar-thumb {
  background-color: gold;
  border-radius: 384px;
}

.media-scroller::-webkit-scrollbar-thumb:hover {
  background-color: rgba(255, 215, 0, 0.75);
}

.media-element {
  display: grid;
  grid-template-rows: min-content;
  gap: var(--_spacer);
  padding: var(--_spacer);
  margin: 12px;
}
.media-element > img {
  inline-size: 100%;
  aspect-ratio: 16 / 16;
  object-fit: cover;
}
.snaps-inline {
  scroll-snap-type: inline mandatory;
  scroll-padding-inline: var(--_spacer, 1rem);
}
.snaps-inline > * {
  scroll-snap-align: start;
}

.media-element img {
  max-width: 100%;
  height: auto;
}

@media (max-width: 767px) {
  .media-scroller {
    grid-auto-columns: 45%;
    overflow-y: hidden;
  }

  .media-element {
    margin: 8px;
  }
}
</style>
