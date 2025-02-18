<script setup>

import SectionHeader from './SectionHeader.vue';

const workProcess = [
    {
        step: '01',
        title: 'Understanding Your Needs & Goals',
        description: 'We begin by thoroughly discussing your project requirements, objectives, and expectations. This helps us define the scope, key features, and technical specifications needed for success.',
        icon: 'fa-solid fa-handshake'
    },
    {
        step: '02',
        title: 'Strategic Planning & Conceptualization',
        description: 'Our team crafts a tailored project strategy, including wireframes, design mockups, and a roadmap to ensure a smooth development process aligned with your vision.',
        icon: 'fa-solid fa-sitemap'
    },
    {
        step: '03',
        title: 'Agile Development & Implementation',
        description: 'We start building your project using the latest technologies, following best coding practices and agile methodologies to ensure efficiency and flexibility.',
        icon: 'fa-solid fa-code'
    },
    {
        step: '04',
        title: 'Rigorous Testing & Quality Assurance',
        description: 'Before delivery, we conduct thorough testing, debugging, and optimizations to ensure performance, security, and a seamless user experience across all devices and platforms.',
        icon: 'fa-solid fa-microscope'
    },
    {
        step: '05',
        title: 'Client Review & Feedback Integration',
        description: 'We present the project to you for review, gather feedback, and make necessary refinements to ensure the final product aligns perfectly with your vision and business needs.',
        icon: 'fa-solid fa-comments'
    },
    {
        step: '06',
        title: 'Final Delivery & Deployment',
        description: 'Once everything is approved, we deliver the final product, assist with deployment, and provide any necessary post-launch support for a smooth transition.',
        icon: 'fa-solid fa-rocket'
    }
];

</script>

<template>

    <section  class="container mx-auto px-4 animate-on-scroll">

        <!-- Header Section -->
        <SectionHeader size="large">
            <template #subtitle>
                Our Work Process
            </template>
            <template #title>
                A Structured Approach for Outstanding Results
            </template>
            <template #description>
                Our streamlined process ensures efficiency, transparency, and high-quality outcomes at every stage of your project.
            </template>
        </SectionHeader>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
            <div 
                class="relative p-6 pb-10 flex gap-4 border border-gray-200 rounded-lg hover:shadow-lg transition-shadow duration-300 bg-gradient-to-br from-blue-50 to-purple-50" 
                v-for="process in workProcess" 
                :key="process.step"
            >
                <div class="text-purple-600 text-2xl p-4 rounded-full bg-purple-100 self-start w-14 h-14 grid place-items-center">
                    <i :class="process.icon"></i>
                </div>
                <div class="flex-1">
                    <h3 class="font-bold mb-2">{{ process.title }}</h3>
                    <p class="text-gray-600 text-sm">{{ process.description }}</p>
                </div>
                <span class="block absolute right-3 bottom-3 text-4xl font-bold bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-transparent opacity-30">
                    {{ process.step }}
                </span>
            </div>
        </div>

    </section>

</template>