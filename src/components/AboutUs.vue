<script setup>

import SectionHeader from './SectionHeader.vue';

const areasOfExpertise = [
    'Web Services',
    'Cloud Solutions',
    'API Integration',
    'Digital Commerce',
    'Educational Tech',
    'Enterprise Solutions',
    'Software Platforms'
];

</script>

<template>
    <section  class="container mx-auto px-4 animate-on-scroll">

        <!-- Header Section -->
        <SectionHeader size="large">
            <template #subtitle>
                Our Story
            </template>
            <template #title>
                Building Tomorrow's Solutions
            </template>
            <template #description>
                We combine innovation with expertise to create digital solutions that transform businesses.
            </template>
        </SectionHeader>

        <!-- Main Content Grid -->
        <div class="grid lg:grid-cols-2 gap-8">
            <!-- Identity Card -->
            <div class="bg-gradient-to-br from-blue-50 to-purple-50 rounded-3xl p-8 border border-gray-100 backdrop-blur-lg">
                <div class="flex items-center mb-6">
                    <div class="w-12 h-12 flex items-center justify-center rounded-2xl bg-gray-50">
                        <svg class="w-6 h-6 text-blue-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z" />
                        </svg>
                    </div>
                    <h3 class="ml-4 text-2xl font-bold text-gray-800">Our Identity</h3>
                </div>
                
                <div class="space-y-6">
                    <p class="text-gray-600 leading-relaxed">
                        At Cybernest, we are a technology and software solutions company based in northern Morocco, dedicated to innovation and excellence. Our mission is to empower businesses and drive their growth by leveraging cutting-edge technology. With a forward-thinking approach and a commitment to quality, we help our partners navigate the digital landscape, streamline operations, and unlock new opportunities for success.
                        At Cybernest, we believe that technology is not just a tool but a catalyst for progress. By combining expertise, creativity, and a passion for innovation, we deliver solutions that make a lasting impact. Partner with us, and let's build the future together.
                    </p>
                    
                    <div class="bg-slate-50 rounded-2xl p-6">
                        <h4 class="font-semibold text-gray-800 mb-4">Areas of Excellence</h4>
                        <div class="flex flex-wrap gap-3">
                            <span v-for="area in areasOfExpertise" 
                                    :key="area" 
                                    class="px-4 py-2 bg-white border border-gray-200 rounded-xl text-sm text-gray-700 shadow-sm">
                                {{ area }}
                            </span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Vision Card -->
            <div class="bg-gradient-to-br from-blue-50 to-purple-50 rounded-3xl p-8 border border-gray-100">
                <div class="flex items-center mb-6">
                    <div class="w-12 h-12 flex items-center justify-center rounded-2xl bg-gray-50">
                        <svg class="w-6 h-6 text-blue-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" />
                        </svg>
                    </div>
                    <h3 class="ml-4 text-2xl font-bold text-gray-800">Our Vision</h3>
                </div>

                <div class="space-y-6">
                    <div v-for="(item, index) in [
                        { title: 'Digital Transformation', desc: 'Empowering businesses with cutting-edge digital solutions' },
                        { title: 'Custom Innovation', desc: 'Developing tailored solutions that address unique challenges' },
                        { title: 'Growth Partnership', desc: 'Supporting your journey with dedicated expertise' },
                        { title: 'Sustainable Success', desc: 'Building long-term strategies for continuous growth' }
                    ]" :key="index" 
                    class="flex items-center p-4 rounded-2xl hover:bg-slate-50 transition-colors duration-300">
                        <span class="w-8 h-8 flex items-center justify-center rounded-lg bg-gradient-to-r from-blue-600 to-purple-600 text-white text-sm font-bold">
                            {{ index + 1 }}
                        </span>
                        <div class="ml-4">
                            <h4 class="font-semibold text-gray-800">{{ item.title }}</h4>
                            <p class="text-gray-600 text-sm mt-1">{{ item.desc }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </section>
</template>