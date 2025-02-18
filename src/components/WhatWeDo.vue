<script setup>

import SectionHeader from './SectionHeader.vue';

const services = [
    {
        title: "Custom Development",
        description: "We create custom solutions from scratch to address your specific business needs, whether it's a web app, system integration, or enterprise solution, ensuring scalability, security, and performance."
    },
    {
        title: "Modern Design",
        description: "We design visually stunning and responsive user interfaces that provide seamless experiences across all devices, ensuring your product is both engaging and functional."
    },
    {
        title: "Digital Marketing",
        description: "Our digital marketing strategies help enhance your online visibility, attract targeted traffic, and convert leads into loyal customers through SEO, PPC, and content marketing."
    },
    {
        title: "CMS Store and Website Development",
        description: "We build scalable, user-friendly online stores and websites on platforms like Shopify and WordPress, ensuring that your site is easy to manage and optimized for performance."
    },
    {
        title: "Fast Delivery",
        description: "We prioritize quick delivery without compromising quality, ensuring that your project is completed on time and to the highest standards."
    },
    {
        title: "Ongoing Support",
        description: "Our ongoing support ensures your digital products remain secure, updated, and optimized, providing you with peace of mind as your business evolves."
    }
];



</script>

<template>

    <section class="py-16 bg-gradient-to-br from-blue-50 to-purple-50 animate-on-scroll">

        <div class="container mx-auto px-4">
            <!-- Section Header -->
            <SectionHeader>
                <template #subtitle>
                    What We Do
                </template>
                <template #title>
                    Innovative Solutions for a Digital World
                </template>
                <template #description>
                    From web development to AI-driven insights, we craft tailored technology solutions that empower businesses to thrive in the digital age.
                </template>
            </SectionHeader>

            <div class="space-y-10">

                <p class="relative text-center text-gray-500 pb-8">
                    At <span class="font-black bg-clip-text text-transparent bg-gradient-to-r from-blue-600 to-purple-600">Cybernest</span>, we offer a range of services including Custom Development, Modern Design, Digital Marketing, and CMS Development. Our team is dedicated to delivering tailored, high-quality solutions that drive business growth, with fast delivery and ongoing support to ensure your success every step of the way.
                    <span class="absolute left-1/2 -translate-x-1/2 bottom-0 bg-purple-300 h-0.5 w-20"></span>
                </p>

                <div class="grid grid-cols-1 sm:grid-cols-2 gap-10">
                    <div class="flex gap-4" v-for="service in services" :key="service">
                        <span class="w-8 h-8 shrink-0 text-purple-600 rounded-full bg-purple-100 grid place-items-center">
                            <i class="fa-solid fa-check text-sm"></i>
                        </span>
                        <div class="space-y-1">
                            <h3 class="text-xl font-bold text-gray-700">{{ service.title }}</h3>
                            <p class="text-gray-500">{{ service.description }}</p>
                        </div>
                    </div>
                </div>

            </div>
        </div>

    </section>

</template>