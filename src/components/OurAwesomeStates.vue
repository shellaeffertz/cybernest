<script setup>
import { onMounted, ref } from 'vue';

const stats = [
  {
    value: '50+',
    label: 'Successful Projects Delivered',
    icon: 'fas fa-check-circle',
    target: 50
  },
  {
    value: '100%',
    label: 'Client Satisfaction Rate',
    icon: 'fas fa-star',
    target: 100
  },
  {
    value: '30+',
    label: 'Years of Combined Expertise',
    icon: 'fas fa-award',
    target: 30
  },
  {
    value: '24/7',
    label: 'Dedicated Support Availability',
    icon: 'fas fa-headset',
    target: null
  },
  {
    value: '10+',
    label: 'Industries Served',
    icon: 'fas fa-industry',
    target: 10
  },
  {
    value: '$20M+',
    label: 'Revenue Generated for Clients',
    icon: 'fas fa-chart-line',
    target: 20,
    prefix: '$',
    suffix: 'M+'
  }
];

const observeElements = (elements) => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const targetElement = entry.target;
        const targetValue = parseInt(targetElement.getAttribute('target-number'));
        const prefix = targetElement.getAttribute('data-prefix') || '';
        const suffix = targetElement.getAttribute('data-suffix') || '+';
        
        if (targetValue) {
          animateValue(targetElement, 0, targetValue, 2000, prefix, suffix);
        }
        
        observer.unobserve(targetElement);
      }
    });
  }, {
    threshold: 0.1,
    rootMargin: '0px'
  });

  elements.forEach(element => {
    observer.observe(element);
  });
};

const animateValue = (element, start, end, duration, prefix = '', suffix = '+') => {
  let startTimestamp = null;
  const step = (timestamp) => {
    if (!startTimestamp) startTimestamp = timestamp;
    const progress = Math.min((timestamp - startTimestamp) / duration, 1);
    const currentValue = Math.floor(progress * (end - start) + start);
    element.innerHTML = `${prefix}${currentValue}${suffix}`;
    if (progress < 1) {
      window.requestAnimationFrame(step);
    }
  };
  
  window.requestAnimationFrame(step);
};

onMounted(() => {
  const elements = document.querySelectorAll('.animate-stat');
  observeElements(elements);
});
</script>

<template>
  <section class="relative animate-on-scroll">
    <img class="relative w-full h-[1300px] sm:h-[550px] object-cover object-center" src="/images/stats.jpg" alt="stats background image" />
    <div class="absolute top-0 left-0 w-full h-full bg-gradient-to-r from-blue-600 to-purple-600 opacity-80"></div>
    <div class="absolute top-10 px-8 w-full z-40 space-y-8 flex flex-col items-start sm:items-center">
      <h1 class="text-white text-4xl font-bold">Our Awesome Stats</h1>
      <div class="grid grid-cols-1 sm:grid-cols-3 gap-8">
        <div class="relative group p-4 bg-white flex flex-col items-center gap-4" v-for="stat in stats" :key="stat.label">
          <span class="absolute top-0 left-0 w-1 duration-300 h-0 bg-purple-600 group-hover:h-full"></span>
          <span class="absolute bottom-0 right-0 w-1 duration-300 h-0 bg-blue-600 group-hover:h-full"></span>
          <i :class="stat.icon" class="bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-transparent text-3xl"></i>
          <span 
            class="font-black text-4xl bg-gradient-to-r from-blue-600 to-purple-600 bg-clip-text text-transparent animate-stat" 
            :target-number="stat.target"
            :data-prefix="stat.prefix || ''"
            :data-suffix="stat.suffix || '+'"
          >
            {{ stat.target ? (stat.prefix || '') + '0' + (stat.suffix || '+') : stat.value }}
          </span>
          <span class="text-gray-700 text-xl font-bold">{{ stat.label }}</span>
        </div>
      </div>
    </div> 
  </section>
</template>