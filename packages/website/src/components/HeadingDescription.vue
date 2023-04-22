<template>
    <div class="mx-auto max-w-2xl md:text-center">
        <h2 class="font-bold text-3xl tracking-tight sm:text-4xl">
            <slot name="heading"></slot>
        </h2>
        <p class="mt-4 text-lg tracking-tight text-slate-300">
            <slot name="description"></slot>
        </p>
    </div>
</template>