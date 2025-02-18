<script setup>

import Cybernest from './Cybernest.vue';

const currentYear = new Date().getFullYear();

const links = {
    title: 'Entreprise',
    links: [
        { name: 'About Us', href: '#about' },
        { name: 'Our Team', href: '#team' },
        { name: 'Services', href: '#services' },
        { name: 'Our Partners', href: '#partners' },
        { name: 'Contact', href: '#contact' }
    ]
};

const services = {
    title: 'Services',
    items: [
        'Services web',
        'CMS developement',
        'Cloud',
        'E-commerce',
        'E-learning'
    ]
};

const contactInfo = {
    address: 'Tetouan, Morocco',
    email: 'contact@cybernest.com',
    phone: '+212 756421236'
};

</script>

<template>
    <footer class="bg-gradient-to-br from-blue-50 to-purple-50">
        <div class="container mx-auto px-4 py-12">
            <div class="grid md:grid-cols-4 gap-8">
                <!-- Company Info -->
                <div class="col-span-1">
                    <div class="space-y-4">
                        <Cybernest />
                        <p class="text-gray-600 text-sm leading-relaxed">
                            Your trusted technology partner for digital transformation and innovation.
                        </p>
                    </div>
                </div>

                <!-- Services -->
                <div class="col-span-1">
                    <div class="space-y-4">
                        <h4 class="text-sm font-semibold text-gray-900 uppercase tracking-wider">{{ services.title }}</h4>
                        <ul class="space-y-2">
                            <li v-for="service in services.items" :key="service">
                                <span class="text-gray-600 text-sm block">
                                    {{ service }}
                                </span>
                            </li>
                        </ul>
                    </div>
                </div>

                <!-- Links -->
                <div class="col-span-1">
                    <div class="space-y-4">
                        <h4 class="text-sm font-semibold text-gray-900 uppercase tracking-wider">{{ links.title }}</h4>
                        <ul class="space-y-2">
                            <li v-for="link in links.links" :key="link.name">
                                <a :href="link.href" class="text-gray-600 hover:text-indigo-600 text-sm transition-colors duration-200">
                                    {{ link.name }}
                                </a>
                            </li>
                        </ul>
                    </div>
                </div>

                <!-- Contact Info -->
                <div class="col-span-1">
                    <div class="space-y-4">
                        <h4 class="text-sm font-semibold text-gray-900 uppercase tracking-wider">Contact</h4>
                        <ul class="space-y-3">
                            <li class="flex items-start space-x-3">
                                <svg class="h-5 w-5 text-gray-400 mt-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                                </svg>
                                <span class="text-gray-600 text-sm">{{ contactInfo.address }}</span>
                            </li>
                            <li class="flex items-center space-x-3">
                                <svg class="h-5 w-5 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"/>
                                </svg>
                                <a href="mailto:contact@asitech.mr" class="text-gray-600 hover:text-indigo-600 text-sm transition-colors duration-200">
                                    {{ contactInfo.email }}
                                </a>
                            </li>
                            <li class="flex items-center space-x-3">
                                <svg class="h-5 w-5 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/>
                                </svg>
                                <span class="text-gray-600 text-sm">{{ contactInfo.phone }}</span>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- Copyright -->
            <div class="mt-12 pt-8 border-t border-gray-100">
                <p class="text-center text-gray-500 text-sm">
                    © {{ currentYear }} Cybernest. All rights reserved.
                </p>
            </div>
        </div>
    </footer>
</template>