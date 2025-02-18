<script setup>

</script>

<template>

    <header class="mb-16">
        <div class="flex flex-col gap-3">
            <div class="flex items-center gap-3">
                <div class="relative">
                    <div class="w-8 h-8 rotate-45 bg-gradient-to-r from-blue-600 to-purple-600 opacity-20"></div>
                    <div class="w-4 h-4 rotate-45 bg-gradient-to-r from-blue-600 to-purple-600 absolute top-2 left-2"></div>
                </div>
                <span class="bg-clip-text text-transparent bg-gradient-to-r from-blue-600 to-purple-600 font-semibold">
                    <slot name="subtitle" />
                </span>
            </div>
            <h2 class="text-3xl md:text-5xl font-bold text-gray-800">
                <slot name="title" />
                <span class="relative inline-block">
                    <span class="absolute -bottom-2 left-0 w-full h-2 bg-gradient-to-r from-blue-600 to-purple-600 skew-x-12"></span>
                </span>
            </h2>
            <p class="text-gray-500 text-base md:text-lg max-w-3xl">
                <slot name="description" />
            </p>
        </div>
    </header>

</template>