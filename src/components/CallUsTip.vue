<script setup>

import { ref, onMounted } from 'vue';

const phoneNumber = "+212 756421236";

const showMessage = ref(false);

onMounted(() => {
    setInterval(() => {
        showMessage.value = !showMessage.value;
    }, 5000);
});

</script>

<template>
    <div class="fixed top-0 left-0 z-50 w-full bg-gradient-to-r from-blue-600 to-purple-600">
        <div class="h-10 container mx-auto flex items-center justify-center gap-4 px-4 text-white overflow-hidden">
            <button @click="showMessage = !showMessage" class="text-white">
                <i class="fa-solid fa-arrow-left"></i>
            </button>
            <div class="relative h-full min-w-[550px]">
                <p 
                    :class="{'translate-y-0': showMessage, '-translate-y-full': !showMessage}" 
                    class="absolute left-1/2 -translate-x-1/2 top-0 h-full grid place-items-center text-sm font-medium transition-transform duration-300"
                >
                    Ready to transform your digital presence?
                </p>
                <div 
                    :class="{'translate-y-0': !showMessage, 'translate-y-full': showMessage}"
                    class="absolute left-1/2 -translate-x-1/2 top-0  h-full grid place-items-center transition-transform duration-300"
                >
                    <a 
                        :href="`tel:${phoneNumber}`"
                        class="flex items-center gap-2 text-sm font-semibold transition-colors hover:text-gray-200"
                    >
                        <i class="fa-solid fa-phone text-xs"></i>
                        <span>{{ phoneNumber }}</span>
                    </a>
                </div>
            </div>
            <button @click="showMessage = !showMessage" class="text-white">
                <i class="fa-solid fa-arrow-right"></i>
            </button>
        </div>
    </div>
</template>