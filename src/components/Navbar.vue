<script setup>

import { ref } from 'vue';
import Cybernest from './Cybernest.vue';

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
};

const links = [
   {name: 'About Us',  path: '#about'},
   {name: 'Our Team',  path: '#team'},
   {name: 'Services',  path: '#services'},
   {name: 'Partners',  path: '#partners'},
   {name: 'Contact',  path: '#contact', isContact: true}
];

</script>

<template>
  <nav class="bg-white shadow-md fixed w-full top-10 z-50">
    <div class="container mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <!-- Logo -->
        <Cybernest />

        <!-- Mobile menu button -->
        <div class="flex md:hidden">
          <button 
            @click="toggleMenu"
            class="inline-flex items-center justify-center p-2 rounded-md text-gray-700 hover:text-blue-600 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-blue-500"
            aria-label="Toggle menu"
          >
            <svg 
              class="h-6 w-6" 
              :class="{'hidden': isMenuOpen, 'block': !isMenuOpen }"
              stroke="currentColor" 
              fill="none" 
              viewBox="0 0 24 24"
            >
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
            <svg 
              class="h-6 w-6" 
              :class="{'block': isMenuOpen, 'hidden': !isMenuOpen }"
              stroke="currentColor" 
              fill="none" 
              viewBox="0 0 24 24"
            >
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>

        <!-- Desktop menu with special contact styling -->
        <div class="hidden md:flex md:items-center md:space-x-8">
          <a 
            v-for="link in links" 
            :key="link.name" 
            :href="link.path"
            :class="[
              link.isContact 
                ? 'bg-blue-600 text-white hover:bg-blue-700 px-6' 
                : 'text-gray-700 hover:text-blue-600',
              'py-2 rounded-md text-sm font-medium transition-colors duration-200'
            ]"
          >
            {{ link.name }}
          </a>
        </div>
      </div>
    </div>

    <!-- Mobile menu with special contact styling -->
    <div 
      :class="{'block': isMenuOpen, 'hidden': !isMenuOpen}" 
      class="md:hidden"
    >
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3 bg-white border-t">
        <a 
          v-for="link in links" 
          :key="link.name" 
          :href="link.path"
          :class="[
            link.isContact 
              ? 'bg-blue-600 text-white hover:bg-blue-700' 
              : 'text-gray-700 hover:text-blue-600',
            'block px-3 py-2 rounded-md text-base font-medium transition-colors duration-200'
          ]"
        >
          {{ link.name }}
        </a>
      </div>
    </div>
  </nav>
</template>

<style scoped>
nav {
  transition: all 0.3s ease;
}

@media (max-width: 768px) {
  nav {
    position: relative;
  }
}
</style>