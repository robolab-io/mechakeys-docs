<template>
  <div data-transition-wrap>
    <Hero />

    <section id="features" class="py-20 sm:py-32" aria-label="Description of the features in MechaKeys">
      <Section>
        <HD>
          <template #heading>
            Customize your PC boundlessly
          </template>
          <template #description>
            MechaKeys gives you an open and unified environment to build on. Use what you need, or create your own
            integrations easily.
          </template>
        </HD>

        <div class="mt-20">
          <div class="sm:grid sm:grid-cols-3 sm:gap-x-8 flex flex-col gap-8">
            <div
              class="relative bg-[var(--app-base2)] p-6 rounded-2xl border-solid border-[1px] border-[var(--borders-base1)] shadow-2xl">
              <div class="w-9 h-9 flex items-center justify-center rounded-xl bg-[var(--brand)]">
                <AdjustmentsVerticalIcon class="h-6 w-6" />
              </div>
              <h3 class="mt-6 text-sm font-medium text-[var(--brand)]">Mouse and Keyboard Sounds</h3>
              <p class="mt-2 text-xl font-medium text-slate-100">Play your way with the best sound simulator available.
              </p>
              <p class="mt-4 text-sm text-slate-300">With separate volumes for mouse and keyboard sounds, options for
                stereo
                spread, panning, and a community storefront. <span
                  class="ml-1 text-xs rounded-full bg-[var(--app-fore4)] px-1 uppercase font-bold text-white">Soon</span>
              </p>
            </div>

            <div
              class="relative bg-[var(--app-base2)] p-6 rounded-2xl border-solid border-[1px] border-[var(--borders-base1)] shadow-2xl">
              <div class="w-9 h-9 flex items-center justify-center rounded-xl bg-[var(--brand)]">
                <PhotoIcon class="h-6 w-6" />
              </div>
              <h3 class="mt-6 text-sm font-medium text-[var(--brand)]">Overlays and Wallpapers</h3>
              <p class="mt-2 text-xl font-medium text-slate-100">Create your own completely custom wallpapers and
                overlays.
              </p>
              <p class="mt-4 text-sm text-slate-300">Supercharge your desktop. Play any video you want and embed any
                website
                you like using HTML, CSS, and Javascript.</p>
            </div>

            <div
              class="relative bg-[var(--app-base2)] p-6 rounded-2xl border-solid border-[1px] border-[var(--borders-base1)] shadow-2xl">
              <div class="w-9 h-9 flex items-center justify-center rounded-xl bg-[var(--brand)]">
                <CodeBracketSquareIcon class="h-6 w-6" />
              </div>
              <h3 class="mt-6 text-sm font-medium text-[var(--brand)]">Extensions</h3>
              <p class="mt-2 text-xl font-medium text-slate-100">Integrate your app with the MechaKeys API.</p>
              <p class="mt-4 text-sm text-slate-300">Developers can build using the MechaKeys Events API to extend the
                functionality of your mouse and keyboard.</p>
            </div>
          </div>
        </div>
      </Section>
    </section>

    <section id="testimonial" class="py-20 sm:py-32" aria-label="User testimonials for MechaKeys">
      <Section>
        <HD>
          <template #heading>
            Loved by users worldwide
          </template>
          <template #description>
            From gamers and streamers, bloggers and developers, enthusiasts and more.
          </template>
        </HD>

        <ul role="list"
          class="mx-auto mt-16 grid max-w-2xl grid-cols-1 gap-6 sm:gap-8 lg:mt-20 lg:max-w-none lg:grid-cols-3">
          <li>
            <ul role="list" class="flex flex-col gap-y-6 sm:gap-y-8">
              <li>
                <figure
                  class="relative rounded-2xl bg-[var(--app-base2)] p-6 shadow-2xl border-solid border-[1px] border-[var(--borders-base1)]">
                  <svg aria-hidden="true" width="105" height="78"
                    class="absolute left-6 top-6 fill-[var(--app-fore2)] opacity-50">
                    <path
                      d="M25.086 77.292c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622C1.054 58.534 0 53.411 0 47.686c0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C28.325 3.917 33.599 1.507 39.324 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Zm54.24 0c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622-2.11-4.52-3.164-9.643-3.164-15.368 0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C82.565 3.917 87.839 1.507 93.564 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Z">
                    </path>
                  </svg>
                  <blockquote class="relative">
                    <p class="text-lg tracking-tight text-slate-300">I swear I can't type a message without MechaKeys
                      anymore</p>
                  </blockquote>
                  <figcaption class="relative mt-6 flex items-center justify-between pt-6">
                    <div>
                      <div class="font-display text-base text-slate-100">@veenovas</div>
                      <div class="mt-1 text-sm text-slate-300">Twitter</div>
                    </div>
                  </figcaption>
                </figure>
              </li>

              <li>
                <figure
                  class="relative rounded-2xl bg-[var(--app-base2)] p-6 shadow-2xl border-solid border-[1px] border-[var(--borders-base1)]">
                  <svg aria-hidden="true" width="105" height="78"
                    class="absolute left-6 top-6 fill-[var(--app-fore2)] opacity-50">
                    <path
                      d="M25.086 77.292c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622C1.054 58.534 0 53.411 0 47.686c0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C28.325 3.917 33.599 1.507 39.324 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Zm54.24 0c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622-2.11-4.52-3.164-9.643-3.164-15.368 0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C82.565 3.917 87.839 1.507 93.564 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Z">
                    </path>
                  </svg>
                  <blockquote class="relative">
                    <p class="text-lg tracking-tight text-slate-300">MechaKeys makes your keyboard clicky. good asmr ngl
                    </p>
                  </blockquote>
                  <figcaption class="relative mt-6 flex items-center justify-between pt-6">
                    <div>
                      <div class="font-display text-base text-slate-100">@GI58424124</div>
                      <div class="mt-1 text-sm text-slate-300">Twitter</div>
                    </div>
                  </figcaption>
                </figure>
              </li>
            </ul>
          </li>

          <li>
            <ul role="list" class="flex flex-col gap-y-6 sm:gap-y-8">
              <li>
                <figure
                  class="relative rounded-2xl bg-[var(--app-base2)] p-6 shadow-2xl border-solid border-[1px] border-[var(--borders-base1)]">
                  <svg aria-hidden="true" width="105" height="78"
                    class="absolute left-6 top-6 fill-[var(--app-fore2)] opacity-50">
                    <path
                      d="M25.086 77.292c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622C1.054 58.534 0 53.411 0 47.686c0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C28.325 3.917 33.599 1.507 39.324 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Zm54.24 0c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622-2.11-4.52-3.164-9.643-3.164-15.368 0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C82.565 3.917 87.839 1.507 93.564 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Z">
                    </path>
                  </svg>
                  <blockquote class="relative overflow-hidden aspect-video rounded-xl">
                    <iframe class="absolute inset-0 w-full h-full" width="560" height="315"
                      src="https://www.youtube.com/embed/5qOMPkvpo90?controls=0" title="YouTube video player"
                      frameborder="0"
                      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                      allowfullscreen></iframe>
                  </blockquote>
                  <figcaption class="relative mt-6 flex items-center justify-between pt-6">
                    <div>
                      <div class="font-display text-base text-slate-100">@Vend</div>
                      <div class="mt-1 text-sm text-slate-300">YouTube</div>
                    </div>
                  </figcaption>
                </figure>
              </li>

              <li>
                <figure
                  class="relative rounded-2xl bg-[var(--app-base2)] p-6 shadow-2xl border-solid border-[1px] border-[var(--borders-base1)]">
                  <svg aria-hidden="true" width="105" height="78"
                    class="absolute left-6 top-6 fill-[var(--app-fore2)] opacity-50">
                    <path
                      d="M25.086 77.292c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622C1.054 58.534 0 53.411 0 47.686c0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C28.325 3.917 33.599 1.507 39.324 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Zm54.24 0c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622-2.11-4.52-3.164-9.643-3.164-15.368 0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C82.565 3.917 87.839 1.507 93.564 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Z">
                    </path>
                  </svg>
                  <blockquote class="relative overflow-hidden aspect-video rounded-xl">
                    <iframe class="absolute inset-0 w-full h-full" width="560" height="315"
                      src="https://www.youtube.com/embed/tPFySY0IEsY" title="YouTube video player" frameborder="0"
                      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                      allowfullscreen></iframe>
                  </blockquote>
                  <figcaption class="relative mt-6 flex items-center justify-between pt-6">
                    <div>
                      <div class="font-display text-base text-slate-100">@gmpSNZ</div>
                      <div class="mt-1 text-sm text-slate-300">YouTube</div>
                    </div>
                  </figcaption>
                </figure>
              </li>
            </ul>
          </li>

          <li>
            <ul role="list" class="flex flex-col gap-y-6 sm:gap-y-8">
              <li>
                <figure
                  class="relative rounded-2xl bg-[var(--app-base2)] p-6 shadow-2xl border-solid border-[1px] border-[var(--borders-base1)]">
                  <svg aria-hidden="true" width="105" height="78"
                    class="absolute left-6 top-6 fill-[var(--app-fore2)] opacity-50">
                    <path
                      d="M25.086 77.292c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622C1.054 58.534 0 53.411 0 47.686c0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C28.325 3.917 33.599 1.507 39.324 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Zm54.24 0c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622-2.11-4.52-3.164-9.643-3.164-15.368 0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C82.565 3.917 87.839 1.507 93.564 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Z">
                    </path>
                  </svg>
                  <blockquote class="relative">
                    <p class="text-lg tracking-tight text-slate-300">mechakeys was the goat before i had a mechanical kb
                    </p>
                  </blockquote>
                  <figcaption class="relative mt-6 flex items-center justify-between pt-6">
                    <div>
                      <div class="font-display text-base text-slate-100">@oykvico</div>
                      <div class="mt-1 text-sm text-slate-300">Twitter</div>
                    </div>
                  </figcaption>
                </figure>
              </li>

              <li>
                <figure
                  class="relative rounded-2xl bg-[var(--app-base2)] p-6 shadow-2xl border-solid border-[1px] border-[var(--borders-base1)]">
                  <svg aria-hidden="true" width="105" height="78"
                    class="absolute left-6 top-6 fill-[var(--app-fore2)] opacity-50">
                    <path
                      d="M25.086 77.292c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622C1.054 58.534 0 53.411 0 47.686c0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C28.325 3.917 33.599 1.507 39.324 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Zm54.24 0c-4.821 0-9.115-1.205-12.882-3.616-3.767-2.561-6.78-6.102-9.04-10.622-2.11-4.52-3.164-9.643-3.164-15.368 0-5.273.904-10.396 2.712-15.368 1.959-4.972 4.746-9.567 8.362-13.786a59.042 59.042 0 0 1 12.43-11.3C82.565 3.917 87.839 1.507 93.564 0l11.074 13.786c-6.479 2.561-11.677 5.951-15.594 10.17-3.767 4.219-5.65 7.835-5.65 10.848 0 1.356.377 2.863 1.13 4.52.904 1.507 2.637 3.089 5.198 4.746 3.767 2.41 6.328 4.972 7.684 7.684 1.507 2.561 2.26 5.5 2.26 8.814 0 5.123-1.959 9.19-5.876 12.204-3.767 3.013-8.588 4.52-14.464 4.52Z">
                    </path>
                  </svg>
                  <blockquote class="relative">
                    <p class="text-lg tracking-tight text-slate-300">downloaded MechaKeys itsss sooo gooddddd</p>
                  </blockquote>
                  <figcaption class="relative mt-6 flex items-center justify-between pt-6">
                    <div>
                      <div class="font-display text-base text-slate-100">@MadTingSavage</div>
                      <div class="mt-1 text-sm text-slate-300">Twitter</div>
                    </div>
                  </figcaption>
                </figure>
              </li>
            </ul>
          </li>
        </ul>
      </Section>
    </section>

    <section id="download" class="py-20 sm:py-32" aria-label="Download section for MechaKeys">
      <Section>
        <HD>
          <template #heading>
            Download MechaKeys
          </template>
          <template #description>
            <a tabindex="0"
              href="https://github.com/robolab-io/mechakeys-distro/releases/download/v2.3.1/MechaKeys-installer-win64.exe"
              noreferrer nofollow target="_blank"
              class="mt-2 sm:mb-0 group no-underline inline-flex items-center justify-center rounded-full py-2 px-4 text-sm font-semibold focus:outline-none focus-visible:outline-2 focus-visible:outline-offset-2 bg-[var(--brand)] text-white hover:opacity-80 active:opacity-60 active:text-blue-100 focus-visible:outline-[var(--borders-base1] transition mr-4">
              <ComputerDesktopIcon class="flex-1 w-4 h-4 mr-2" />
              <div class="">Windows Download</div>
            </a>

            <a tabindex="0" href="https://github.com/robolab-io/mechakeys-distro/" noreferrer nofollow target="_blank"
              class="group no-underline inline-flex items-center justify-center rounded-full py-2 px-4 text-sm font-semibold focus:outline-none focus-visible:outline-2 focus-visible:outline-offset-2 bg-[var(--app-base4)] text-white hover:opacity-80 active:opacity-60 active:text-blue-100 focus-visible:outline-[var(--borders-base1] transition mr-4">
              <SparklesIcon class="flex-1 w-4 h-4 mr-2" />
              <div class="">Other Platforms</div>
            </a>
          </template>
        </HD>

      </Section>
    </section>
  </div>
</template>

<script setup>
import Hero from '@/components/HeroSection.vue'
import Section from '@/components/LandingSection.vue'
import HD from '@/components/HeadingDescription.vue'

import { AdjustmentsVerticalIcon, PhotoIcon, CodeBracketSquareIcon, ComputerDesktopIcon, SparklesIcon } from '@heroicons/vue/24/outline'
</script>

<style>
#testimonial {
  background: radial-gradient(ellipse 100% 60% at 50% 50%, rgba(247, 36, 166, 0.07), var(--transparent))
}

#features {
  background: radial-gradient(ellipse 100% 60% at 50% 50%, rgba(187, 36, 247, 0.07), var(--transparent))
}
</style>