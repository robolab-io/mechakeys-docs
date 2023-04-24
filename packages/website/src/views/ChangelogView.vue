<template>
    <main>
        <section id="" class="py-20 sm:py-[142px]" aria-label="Download section for MechaKeys">
            <Section class="">
                <div class="flex mb-32">
                    <div class="hidden w-1/4 sm:flex"></div>
                    <div class="flex flex-1 flex-col items-center justify-center sm:items-start sm:justify-end">
                        <h1 class="max-w-4xl text-4xl font-extrabold tracking-tight sm:text-6xl text-center mb-6">Changelog
                        </h1>
                        <p class="max-w-2xl text-lg tracking-tight text-slate-300 text-center">New updates and improvements
                            to MechaKeys</p>
                    </div>
                </div>

                <ChangelogSection>
                    <template #timestamp>Apr 4, 2023</template>
                    <template #heading>Fresh Paint</template>
                    <template #version>Version 2.3.2 - 2.3.5</template>
                    <template #content>
                        <div class="mb-6">MechaKeys received a full redesign for a smoother experience and to align with our
                            mission of being the integrated typing environment.</div>

                        <div class="mb-6">Some noteable changes:</div>
                        <ul class="list-disc pl-[1.25rem]">
                            <li class="">Experiments are much easier to use, with clearer instructions and more complete interfaces</li>
                            <li class="">A brand new Typing Test page with four presets to choose from</li>
                            <li class="">More reliable syncing, achievement claiming, and error handling</li>
                        </ul>
                    </template>
                </ChangelogSection>
            </Section>
        </section>
    </main>
</template>

<script setup>
import Section from '@/components/LandingSection.vue'
import ChangelogSection from '@/components/ChangelogSection.vue'
</script>