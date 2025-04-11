<script setup>
import {ref} from 'vue';
import ThemeToggler from "@/components/ThemeToggler.vue";

const socialLinks = ref([
  {href: 'https://www.instagram.com/invictusathletics/', icon: 'fa-instagram', color: 'text-pink-400', type: 'brands'},
  // {href: './pages/contact.html', icon: 'fa-envelope', color: 'text-white', type: 'solid'},
  {
    href: 'https://www.facebook.com/invictusathletics/',
    icon: 'fa-square-facebook',
    color: 'text-blue-600',
    type: 'brands'
  },
]);
</script>

<!--absolute bottom-0 right-0-->

<template>
  <footer
      class="w-full dark:bg-black text-center flex flex-col items-center justify-center -z-10">
    <p class="mt-2">
      ELITE TRACK & FIELD CLUB OPERATING OUT OF WATERLOO REGION
    </p>
    <section class="flex gap-3 py-3">
      <a v-for="link in socialLinks" :key="link.href" :href="link.href" target="_blank" class="text-2xl"
         :class="link.color">
        <i :class="[`fa-${link.type}`, link.icon]"></i> </a>
    </section>
    <p>
      <strong>&copy;</strong> INVICTUS ATHLETICS CLUB 2025
    </p>
  </footer>
</template>

<style>

p {
  font-family: "Fjalla One", sans-serif;
  @apply text-lg font-thin dark:text-white text-black
}
</style>