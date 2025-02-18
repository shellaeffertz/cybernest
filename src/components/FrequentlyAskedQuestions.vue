<script setup>

import { ref } from 'vue';
import SectionHeader from './SectionHeader.vue';

const faqs = [
    {
        number: '01',
        question: "What services does Cybernest offer?",
        answer: "Cybernest specializes in Web Development, UI/UX Design, Digital Marketing, AI/ML solutions, and CMS-based store and website development. We deliver innovative and customized digital solutions tailored to your business needs."
    },
    {
        number: '02',
        question: "How does Cybernest approach custom development projects?",
        answer: "We start by understanding your unique requirements, followed by detailed project conception, development, rigorous testing, and final delivery — ensuring quality and client satisfaction every step of the way."
    },
    {
        number: '03',
        question: "Do you provide ongoing support after project completion?",
        answer: "Yes, we offer reliable, long-term support to keep your digital products secure, updated, and running smoothly, helping your business stay ahead of the curve."
    },
    {
        number: '04',
        question: "What platforms do you use for CMS development?",
        answer: "We specialize in building and optimizing online stores and websites using leading CMS platforms like Shopify and WordPress, tailored to your brand and business goals."
    },
    {
        number: '05',
        question: "How long does it take to deliver a project?",
        answer: "Project timelines vary depending on complexity, but our 'Fast Delivery' approach ensures quick turnarounds without compromising on quality or attention to detail."
    },
    {
        number: '06',
        question: "Can Cybernest help with digital marketing strategies?",
        answer: "Absolutely! We offer comprehensive digital marketing strategies to enhance your online presence, drive traffic, and convert leads into loyal customers."
    },
    {
        number: '07',
        question: "What technologies does Cybernest use?",
        answer: "We leverage cutting-edge technologies like React, Vue.js, Laravel, Node.js, Python, and modern design tools such as Figma, Photoshop, and Illustrator to build high-performance solutions."
    },
    {
        number: '08',
        question: "Where can I find reviews about Cybernest?",
        answer: "You can check our ratings and reviews on platforms like Trustpilot, Google, GitHub, and more — see what our clients say about working with us!"
    },
    {
        number: '09',
        question: "What industries does Cybernest work with?",
        answer: "We work with businesses across various industries, including e-commerce, SaaS, fintech, and more, delivering digital solutions that drive growth and innovation."
    },
    {
        number: '10',
        question: "How can I start a project with Cybernest?",
        answer: "Simply reach out to us through our website contact form or email, and we'll get back to you promptly to discuss your requirements and kickstart your project!"
    }
];

const openIndex = ref(null);

const toggleFaq = (index) => {
  openIndex.value = openIndex.value === index ? null : index;
};

</script>

<template>
  <section class="py-16 bg-gradient-to-br from-blue-50 to-purple-50 animate-on-scroll">
    <div class="container mx-auto px-4">

        <!-- Section Header -->
        <SectionHeader>
            <template #subtitle>
                Frequently Asked Questions
            </template>
            <template #title>
                Everything You Need to Know
            </template>
            <template #description>
                We’ve answered some of the most common questions to help you understand how we work and how we can bring value to your business.
            </template>
        </SectionHeader>

      
      <div class="space-y-5">
        <div 
          v-for="(question, index) in faqs" 
          :key="question.number"
          class="border border-gray-200 rounded-lg overflow-hidden bg-white shadow-sm hover:shadow-md transition-shadow duration-300"
        >
          <div 
            @click="toggleFaq(index)"
            class="flex items-start p-6 cursor-pointer"
          >
            <div class="mr-4 text-indigo-500 font-mono text-xl font-bold opacity-75">
              {{ question.number }}
            </div>
            <div class="flex-grow">
              <div class="flex justify-between items-center">
                <h3 class="text-lg font-semibold text-gray-800 pr-4">{{ question.question }}</h3>
                <span class="text-indigo-500 transform transition-transform duration-300" :class="{ 'rotate-180': openIndex === index }">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 20 20" fill="currentColor">
                    <path fill-rule="evenodd" d="M14.707 12.707a1 1 0 01-1.414 0L10 9.414l-3.293 3.293a1 1 0 01-1.414-1.414l4-4a1 1 0 011.414 0l4 4a1 1 0 010 1.414z" clip-rule="evenodd" />
                  </svg>
                </span>
              </div>
              <div
                class="mt-2 transition-all duration-300 overflow-hidden max-h-0"
                :class="{ 'max-h-96 mt-3': openIndex === index }"
              >
                <p class="text-gray-600 leading-relaxed">{{ question.answer }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>