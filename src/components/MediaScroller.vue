<script setup>
import { ref } from 'vue';
import Image1 from "@/assets/scroller/aidenC.jpeg"
import Image2 from "@/assets/scroller/beechy.png"
import Image3 from "@/assets/scroller/coleCoach.png"
import Image4 from "@/assets/scroller/oliv.jpeg"
import Image5 from "@/assets/scroller/threeAmi.jpeg"
import Image6 from "@/assets/scroller/jusKay.jpeg"
import Image7 from "@/assets/scroller/districtC.jpeg"
import Image8 from "@/assets/scroller/alissaRay.jpeg"
import Image9 from "@/assets/scroller/girlRelay.jpeg"
import Image10 from "@/assets/scroller/squad2017.png"
import Image11 from "@/assets/scroller/teamO.jpeg"
import Image12 from "@/assets/scroller/squad2018.jpeg"

const images = ref([
    Image1, Image3, Image4, Image5, Image2, Image6, Image7, Image8, Image9, Image10, Image11, Image12
]);
</script>

<template>
  <div class="media-scroller snaps-inline dark:bg-black">
    <div
        v-for="(img, index) in images"
        :key="index"
        class="media-element">
      <img :src="img" alt="Image" />
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
