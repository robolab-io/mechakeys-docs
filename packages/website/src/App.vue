<template>
	<div class="page-bg contents" :class="{ [page]: true }">
		<Header />
		<RouterView v-slot="{ Component }">
			<transition name="slide-fade" mode="out-in">
				<component :is="Component" />
			</transition>
		</RouterView>
		<Footer />
	</div>
</template>

<script setup>
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import { RouterLink, RouterView, useRoute, useRouter } from 'vue-router'

import { inject } from '@vercel/analytics';
import { onMounted, computed } from 'vue';

const [route] = [useRoute()]
// eslint-disable-next-line no-undef
let page = computed(() => route.fullPath.split('/')[1])

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

.support header {
	display: none;
}

.support footer {
	display: none;
}

::-webkit-scrollbar {
    width: 15px;
    height: 0px;
    background: transparent;
    padding-right: 8px;
  }
  
  ::-webkit-scrollbar-track {
    border-radius: 9999px;
    background: transparent;
  }
  
  ::-webkit-scrollbar-thumb {
    border-radius: 9999px;
    background: var(--scrollbar, var(--app-fore4));
    background-clip: padding-box;
    border: 6px solid rgba(0, 0, 0, 0);
    border-width: 6px;
  }

  ::-webkit-scrollbar-thumb:hover {
    border-width: 5px;
  }
  
  ::-webkit-scrollbar-corner {
    background: transparent;
  }
  
  .page-bg {
	background: var(--app-base6);
  }

  .page-bg.support {
	background: var(--modalBody, var(--app-base3))
  }
</style>
