<script setup>

import { onMounted } from 'vue';
import Home from './components/Home.vue';
import Navbar from './components/Navbar.vue';
import OurTeam from './components/OurTeam.vue';
import AboutUs from './components/AboutUs.vue';
import Contact from './components/Contact.vue';
import WhatWeDo from './components/WhatWeDo.vue';
import CallUsTip from './components/CallUsTip.vue';
import OurPartners from './components/OurPartners.vue';
import WorkProcess from './components/WorkProcess.vue';
import CustomFooter from './components/CustomFooter.vue';
import Technologies from './components/Technologies.vue';
import OurAwesomeStates from './components/OurAwesomeStates.vue';
import ClientsTestimonials from './components/ClientsTestimonials.vue';
import FrequentlyAskedQuestions from './components/FrequentlyAskedQuestions.vue';

const observeElements = (elements) => {

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('is-visible');
        observer.unobserve(entry.target);
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

onMounted(() => {
  const elements = document.querySelectorAll('.animate-on-scroll');
  observeElements(elements);
});

</script>

<template>

  <CallUsTip />

  <Navbar />

  <main class="mt-16">

    <Home />

    <AboutUs class="mt-16"/>

    <WhatWeDo class="mt-16" />

    <OurTeam class="mt-16" />

    <WorkProcess class="mt-16" />

    <Technologies class="mt-16" />

    <ClientsTestimonials class="mt-16" />

    <OurPartners class="mt-16" />

    <OurAwesomeStates />

    <FrequentlyAskedQuestions />

    <Contact />

  </main>

  <CustomFooter />

</template>

<style>


</style>