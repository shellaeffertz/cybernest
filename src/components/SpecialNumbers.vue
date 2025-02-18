<script setup>

import SectionHeader from './SectionHeader.vue';

const stats = [
  {
    value: '50+',
    label: 'Successful Projects Delivered'
  },
  {
    value: '100%',
    label: 'Client Satisfaction Rate'
  },
  {
    value: '30+',
    label: 'Years of Combined Expertise'
  },
  {
    value: '24/7',
    label: 'Dedicated Support Availability'
  },
  {
    value: '10+',
    label: 'Industries Served'
  },
  {
    value: '$20M+',
    label: 'Revenue Generated for Clients'
  }
];


</script>

<template>

    <section class="container mx-auto px-4">

        <!-- Section Header -->
        <SectionHeader>
            <template #subtitle>
                Our Achievements in Numbers
            </template>
            <template #title>
                Milestones That Define Our Success
            </template>
            <template #description>
                From successful projects to satisfied clients, these numbers reflect our dedication, expertise, and impact in the industry.
            </template>
        </SectionHeader>

        <!-- Stats Section - Interactive Circular Design -->
        <div>
            <div class="flex flex-wrap justify-center gap-8">
                <div v-for="stat in stats" :key="stat.label">
                <div class="w-52 h-52 rounded-full border-l-8 border-l-gray-300 bg-gradient-to-br from-blue-50 to-purple-50 shadow-xl flex flex-col items-center justify-center transform transition-all duration-500 hover:scale-105">
                    <h3 class="text-4xl font-bold bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-transparent">
                    {{ stat.value }}
                    </h3>
                    <p class="text-gray-700 font-medium text-center mt-2 px-4 italic">{{ stat.label }}</p>
                </div>
                </div>
            </div>
        </div>

    </section>

</template>