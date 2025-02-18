<script setup>

import SectionHeader from './SectionHeader.vue';

const team = [
  {
    name: 'Khalil KOUISSI',
    role: 'Founder & CEO',
    experience: '8+ years',
    avatar: 'khalil.png',
    motivationalMessage: "Vision drives innovation. Your leadership shapes our success every day."
  },
  {
    name: 'Rachid AIT RHOUDANE',
    role: 'IT Development Director',
    experience: '6+ years',
    avatar: 'rachid.png',
    motivationalMessage: "Your expertise builds the foundation of our digital excellence. Keep inspiring!"
  },
  {
    name: 'Mohamed EL HACHIMI',
    role: 'Shopify & GMC Expert',
    experience: '7+ years',
    avatar: 'mohamed.png',
    motivationalMessage: "E-commerce thrives on precision and creativity—your skills make that possible."
  },
  {
    name: 'Abdelhaq EL ALLAOUI',
    role: 'WordPress & SEO Expert',
    experience: '10+ years',
    avatar: 'abdelhaq.png',
    motivationalMessage: "Your mastery of SEO and WordPress helps businesses shine online. Keep soaring!"
  },
  {
    name: 'Abdelkabir MOKHTAR',
    role: 'Digital Marketing Expert',
    experience: '7+ years',
    avatar: 'abdelkabir.png',
    motivationalMessage: "Marketing is storytelling, and you craft stories that captivate and convert."
  },
  {
    name: 'Yaheya NASRAWI',
    role: 'Copywriter',
    experience: '4+ years',
    avatar: 'yaheya.png',
    motivationalMessage: "Words have power—your creativity brings our brand to life. Keep writing greatness!"
  },
  {
    name: 'Brahim EL SOUSSI',
    role: 'UI/UX Designer',
    experience: '4+ years',
    avatar: 'brahim.png',
    motivationalMessage: "Design is intelligence made visible—your work makes every user experience exceptional."
  },
  {
    name: 'Youssera AL MADANI',
    role: 'UI/UX Designer',
    experience: '2+ years',
    avatar: 'youssera.png',
    motivationalMessage: "Your fresh ideas and creative vision make our designs truly stand out."
  },
  {
    name: 'Ayoub BAHLLOUL',
    role: 'Front-End Developer',
    experience: '4+ years',
    avatar: 'ayoub.png',
    motivationalMessage: "Code is poetry, and your work turns concepts into interactive realities."
  },
  {
    name: 'Hamza EL OUAZANI',
    role: 'Front-End Developer',
    experience: '2+ years',
    avatar: 'hamza.png',
    motivationalMessage: "Your passion for clean, responsive interfaces brings our products to life."
  },
  {
    name: 'Khalid EL ALLAOUI',
    role: 'Back-End Developer',
    experience: '5+ years',
    avatar: 'khalid.png',
    motivationalMessage: "Behind every seamless experience is your solid, reliable code. Keep building magic!"
  },
  {
    name: 'Anas EL KHARRAZ',
    role: 'Back-End Developer',
    experience: '3+ years',
    avatar: 'anas.png',
    motivationalMessage: "Every line of code you write strengthens our digital architecture. Keep it up!"
  },
  {
    name: 'Ahmed SBITTI',
    role: 'Back-End Developer',
    experience: '4+ years',
    avatar: 'ahmed.png',
    motivationalMessage: "Your backend brilliance powers our front-end success. Stay innovative!"
  },
];


</script>

<template>

  <section class="container mx-auto px-4 animate-on-scroll">

      <!-- Section Header -->
       <SectionHeader>
            <template #subtitle>
                Our Team
            </template>
            <template #title>
                Meet Our Team of Experts
            </template>
            <template #description>
                With decades of combined experience, our dedicated professionals bring innovation and excellence to every project we undertake.
            </template>
       </SectionHeader>

      <!-- Team Members Section -->
      <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
        <div class="relative group rounded-xl bg-gradient-to-br from-blue-50 to-purple-50 px-6 py-3 shadow-sm hover:shadow-md transition-all duration-300 overflow-hidden" 
             v-for="member in team" 
             :key="member.name">
            <div class="absolute top-2 right-2 w-20 h-20 bg-white rounded-full shadow-lg overflow-hidden">
              <img class="w-full h-full object-contain transition-transform duration-300 opacity-100 group-hover:scale-105" 
                   :src="`/images/team/${member.avatar}`" 
                   :alt="`${member.name}'s professional photo`" />
            </div>
            <div class="absolute -left-2 -top-0.5 px-4 py-1  bg-gradient-to-r from-blue-600 to-purple-600 rounded-md">
              <span class="block text-xs text-white">
                <span class="font-black">{{ member.experience }}</span> {{ member.experience === 1 ? 'Year' : 'Years' }} of Experience
              </span>
            </div>
            <div class="space-y-4 pt-8">
              <div class="flex flex-col gap-1">
                <h3 class="font-bold text-xl bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-transparent">{{ member.name }}</h3>
                <span class="text-sm text-gray-600 font-medium">{{ member.role }}</span>
              </div>
              <q class="block text-gray-600 text-sm italic leading-relaxed">{{ member.motivationalMessage }}</q>
            </div>
        </div>
      </div>

  </section>

</template>