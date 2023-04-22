<template>
    <div class="bg-[var(--app-base6)]">
        <footer class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
            <!--  sm:flex-row-reverse sm:justify-between -->
            <div class="flex flex-col gap-4 sm:flex-row sm:items-center justify-between py-8">
                <p class="opacity-40 text-xs">
                    Copyright © 2023 Robolab LLC. All rights reserved.
                </p>

                <div class="opacity-40 sm:mt-0 text-xs flex gap-8">
                    <RouterLink to="/terms">Terms</RouterLink>
                    <RouterLink to="/privacy">Privacy</RouterLink>
                </div>
            </div>
        </footer>
    </div>
</template>

<script setup>
import { RouterLink } from 'vue-router'
</script>