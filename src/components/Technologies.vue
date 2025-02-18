<script setup>

import SectionHeader from './SectionHeader.vue';

const technologies = [
    {
        title: "Modern Frontend Frameworks & Libraries",
        tools: ["reactjs.svg", "vue.svg", "angular.svg", "bootstrap.svg", "tailwindcss.svg", "sass.svg"]
    },
    {
        title: "Robust Backend Technologies for Scalable Applications",
        tools: ["laravel.svg", "nodejs.svg", "express.svg", "django.svg", "flask.svg"]
    },
    {
        title: "Efficient Databases & Data Storage Solutions",
        tools: ["mysql.svg", "postgresql.svg", "mongodb.svg", "firebase.svg"]
    },
    {
        title: "Cloud Computing & DevOps for Reliable Deployment",
        tools: ["aws.svg", "digitalocean.svg", "google-cloud.svg", "azure.svg", "docker.svg", "nginx.svg", "apache.svg"]
    },
    {
        title: "Creative UI/UX Design Tools for Stunning Interfaces",
        tools: ["figma.svg", "photoshop.svg", "adobe-illustrator.svg", "after-effects.svg"]
    },
    {
        title: "Powerful CMS & E-Commerce Platforms",
        tools: ["wordpress.svg", "shopify.svg"]
    },
    {
        title: "Digital Marketing & SEO Tools for Growth",
        tools: ["google-shopping.svg", "google-ads.svg", "facebook-ads.webp", "mailchimp.svg"]
    }
];

</script>

<template>

    <section class="py-16 bg-gradient-to-br from-blue-50 to-purple-50 animate-on-scroll">

        <div class="container mx-auto px-4">
            <!-- Section Header -->
            <SectionHeader>
                <template #subtitle>
                    Tools & Technologies
                </template>
                <template #title>
                    Empowering Innovation with Cutting-Edge Technologies
                </template>
                <template #description>
                    We leverage the latest tools and technologies in web development, UI/UX design, digital marketing to deliver high-performance solutions tailored to your needs.
                </template>
            </SectionHeader>

            <div class="space-y-8">
                <div class="space-y-4" v-for="area in technologies" :key="area.title">
                    <h1 class="flex items-center gap-2">
                        <span class="text-xl font-bold text-gray-500">{{ area.title }}</span>
                        <span class="block relative flex-1">
                            <span class="block absolute top-1/2 -translate-y-1/2 right-0 w-full h-0.5 bg-gradient-to-r from-gray-300 to-gray-100"></span>
                        </span>
                    </h1>
                    <div class="flex items-center flex-wrap gap-8">
                        <div class="w-8 h-8" v-for="tool in area.tools" :key="tool">
                            <img class="w-full h-full object-contain object-center" :src="`/images/technologies/${tool}`" :alt="`${tool} image`">
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </section>

</template>