<template>
    <main class="">
        <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8 pb-16 pt-20 text-center lg:pt-28">
            <h1 class="mx-auto max-w-4xl text-4xl font-extrabold tracking-tight sm:text-6xl">The <span
                    class="text-[var(--brand)]">integrated</span> typing environment</h1>
            <p class="mx-auto mt-6 max-w-2xl text-lg tracking-tight text-slate-300">MechaKeys is your ultimate desktop
                customization tool. A mouse and keyboard sound simulator, live wallpapers and overlays, and so much more, all in one app.</p>

            <div class="mx-auto mt-6 max-w-2xl flex-col justify-center sm:flex-row">
                <a tabindex="0"
                    href="https://github.com/robolab-io/mechakeys-distro/releases/download/v2.3.1/MechaKeys-installer-win64.exe"
                    noreferrer nofollow target="_blank"
                    class="mb-2 sm:mb-0 group no-underline inline-flex items-center justify-center rounded-full py-2 px-4 text-sm font-semibold focus:outline-none focus-visible:outline-2 focus-visible:outline-offset-2 bg-[var(--brand)] text-white hover:opacity-80 active:opacity-60 active:text-blue-100 focus-visible:outline-[var(--borders-base1] transition mr-4">
                    <ArrowDownTrayIcon class="flex-1 w-4 h-4 mr-2" />
                    <div class="">Download for Windows</div>
                </a>

                <a tabindex="0"
                    href="https://github.com/robolab-io/mechakeys-distro/releases/download/v2.3.1/MechaKeys-installer-win64.exe"
                    noreferrer nofollow target="_blank"
                    class="group no-underline inline-flex items-center justify-center rounded-full py-2 px-4 text-sm font-semibold focus:outline-none focus-visible:outline-2 focus-visible:outline-offset-2 bg-[var(--app-base4)] text-white hover:opacity-80 active:opacity-60 active:text-blue-100 focus-visible:outline-[var(--borders-base1] transition mr-4">
                    <CodeBracketIcon class="flex-1 w-4 h-4 mr-2" />
                    <div class="">Developer Documentation<span class="ml-2 text-xs rounded-full bg-[var(--app-fore4)] px-2 py-1 uppercase font-bold text-white">Soon</span></div>
                </a>
            </div>
        </div>


        <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8 pb-16 pt-4 text-center lg:pt-8">
            <div class="relative transform-gpu">
                <div class="pointer-events-none mx-auto max-w-4xl absolute inset-5 z-0 rounded-md"
                    style="box-shadow: rgb(255 0 99 / 10%) 0px -40px 900px, rgb(255 56 251 / 20%) 0px 40px 600px"></div>
                <div class="relative mx-auto max-w-4xl overflow-hidden rounded-xl bg-[var(--app-base6)] aspect-[1260/814]">
                    <img src="https://i.imgur.com/MV9kO1R.png"
                        class="absolute inset-0 w-full h-full object-fit scale-[1.005]">
                </div>
            </div>
        </div>

    </main>
</template>

<script setup>
import { ArrowDownTrayIcon, CodeBracketIcon } from '@heroicons/vue/24/outline'
</script>