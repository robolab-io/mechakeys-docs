<template>
  <video class="lobbyVideo" src="https://s3.amazonaws.com/labs.robolab.io/drive/ui/ppbg_s.mp4" autoplay muted loop></video>
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
</script>


<style scoped>
.slide-fade-enter-active {
  transition: all 0.22s cubic-bezier(0,.99,.34,1)
}

.slide-fade-leave-active {
  transition: all 0.22s cubic-bezier(0,.99,.34,1)
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  /* transform: translateY(20px) scale(0.9); */
  transform: translateY(8px);
  opacity: 0;
}

.lobbyVideo {
    position: fixed;
    inset: 0;
    width: 100vw;
    height: 100vh;
    opacity: .08;
    object-fit: cover;
    mix-blend-mode: lighten;
    z-index: 0;
    pointer-events: none;
    user-select: none;
}
</style>
