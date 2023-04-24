<template>
  <Header />
  <RouterView v-slot="{ Component }">
    <transition name="slide-fade" mode="out-in">
      <component :is="Component" />
    </transition>
  </RouterView>
  <Footer />
</template>

<script setup lang="ts">
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import { RouterLink, RouterView } from 'vue-router'

import { inject } from '@vercel/analytics';
import { onMounted } from 'vue';
 
onMounted(() => {
  inject()
})
</script>


<style>
.slide-fade-enter-active {
  transition: all 0.22s cubic-bezier(0, .99, .34, 1)
}

.slide-fade-leave-active {
  transition: all 0.22s cubic-bezier(0, .99, .34, 1)
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  /* transform: translateY(20px) scale(0.9); */
  transform: translateY(8px);
  opacity: 0;
}

@keyframes bounce-img {

  0%,
  100% {
    transform: translateY(12px);
  }

  50% {
    transform: none;
  }
}
</style>
