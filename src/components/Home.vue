<script setup>

import ClipedText from './ClipedText.vue';
import halfFlower from '../assets/half-flower.svg';
import PlateformsRatings from './PlateformsRatings.vue';

const services = [
  {
    name: 'Web Development',
    icon: 'fa-solid fa-code',
    description: 'Creating modern, responsive web applications'
  },
  {
    name: 'UI/UX Design',
    icon: 'fa-solid fa-palette',
    description: 'Crafting beautiful and intuitive user experiences'
  },
  {
    name: 'Digital Marketing',
    icon: 'fa-solid fa-chart-simple',
    description: 'Growing your digital presence and reach'
  },
];

</script>

<template>
  <section class="relative overflow-hidden">

    <!-- Decorative Half-Flower Shape -->
    <div class="absolute -top-52 left-1/2 -translate-x-1/2 w-full flex justify-center" aria-hidden="true">
      <img :src="halfFlower" class="opacity-[0.08]" />
    </div>

    <!-- Main Content -->
    <div class="container mx-auto px-4 pt-16 relative">
      <!-- Hero Section -->
      <div class="text-center mb-20">
        <ClipedText>
          Cybernest
        </ClipedText>
        
        <p class="text-xl text-gray-700 leading-relaxed max-w-2xl mx-auto">
          Cybernest is a technology company based in northern <span class="font-black text-red-500">Mo<span class="text-green-500">roc</span>co</span>, specializing in web development, UI/UX design, and digital solutions. We transform ideas into impactful products, bringing your vision to life with innovation, quality, and creativity
        </p>

        <a href="#contact" 
           class="mt-8 inline-block px-8 py-4 rounded-full bg-gradient-to-r from-blue-600 to-purple-600 text-white font-semibold hover:shadow-lg transform hover:-translate-y-1 transition-all duration-300">
          Get Started
        </a>
      </div>

      <PlateformsRatings />
      
      <!-- Services Section -->
      <div class="mt-32">
        <h2 class="text-4xl font-bold text-center text-gray-800 mb-16">
          Our Services
        </h2>

        <div class="grid md:grid-cols-3 gap-8">
            <div v-for="service in services" 
                :key="service.name"
                class="group bg-gradient-to-br from-blue-50 to-purple-50 p-8 rounded-2xl shadow-sm hover:shadow-xl transition-all duration-300"
            >
                <div class="flex flex-col items-center text-center">
                <div class="w-16 h-16 flex items-center justify-center rounded-full bg-blue-100 group-hover:bg-blue-600 transition-colors duration-300 mb-6">
                    <i :class="[service.icon, 'text-2xl text-blue-600 group-hover:text-white']"></i>
                </div>
                <h3 class="text-xl font-semibold text-gray-800 mb-4">{{ service.name }}</h3>
                <p class="text-gray-600">{{ service.description }}</p>
                </div>
            </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
section {
  background-color: #ffffff;
  min-height: 100vh;
}
</style>