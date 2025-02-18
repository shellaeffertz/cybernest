<script setup>

import SectionHeader from './SectionHeader.vue';

const partners = [
    'freelap.svg',
    'houston.svg',
    'icbo.svg',
    'magnima.svg',
    'seekrz.svg',
    'siemens.svg',
    'spendbitcoins.svg',
    'zeroeyes.svg'
];

</script>

<template>

    <section class="py-16 bg-gradient-to-br from-blue-50 to-purple-50 animate-on-scroll">

        <div class="container mx-auto px-4">

            <!-- Section Header -->
            <SectionHeader>
                <template #subtitle>
                    Our Trusted Partners
                </template>
                <template #title>
                    Building Strong Collaborations
                </template>
                <template #description>
                    We’re proud to work alongside industry leaders and innovators, creating value through lasting partnerships that drive mutual success.
                </template>
            </SectionHeader>

            <div>
                <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-8">
                    <div v-for="partner in partners" 
                        :key="partner" 
                        class="flex items-center justify-center p-6 bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow duration-300 h-[120px] md:h-[120px]">
                        <img 
                        :src="`/images/partners/${partner}`" 
                        :alt="`${partner} logo`"
                        class="max-h-16 w-auto filter grayscale hover:grayscale-0 transition-all duration-300 transform hover:scale-105" 
                        loading="lazy"
                        />
                    </div>
                </div>
            </div>

        </div>

    </section>

</template>