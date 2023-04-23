<template>
    <article class="py-10 sm:flex max-w-7xl">
        <div class="sm:sticky sm:top-28 sm:w-1/4 sm:self-start flex items-center mb-4 sm:mb-0">
            <slot name="timestamp"></slot> 
            <!-- <div class="h-[1px] flex-1 mx-8 bg-white opacity-25"></div> -->
        </div>
        <div class="flex flex-1 flex-col">
            <h2 class="text-3xl font-bold tracking-tight sm:text-3xl flex items-center mb-4">
                <slot name="heading"></slot>
                <span class="ml-2 text-xs rounded-full bg-[var(--app-fore4)] px-2 py-1 font-bold text-white tracking-normal">
                    <slot name="version"></slot>
                </span>
            </h2>
            <div class="break-words max-w-[65ch] leading-8 relative bg-[var(--app-base2)] p-6 rounded-2xl border-solid border-[1px] border-[var(--borders-base1)] shadow-2xl">
                <slot name="content"></slot>
            </div>
        </div>
    </article>
</template>