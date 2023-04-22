<template>
  <Header />
  <RouterView />
  <Footer />
</template>

<script setup lang="ts">
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import { RouterLink, RouterView } from 'vue-router'
</script>


<style scoped></style>
