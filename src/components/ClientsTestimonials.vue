<script setup>

import 'swiper/css';
import 'swiper/css/pagination';

import SectionHeader from './SectionHeader.vue';
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Pagination } from 'swiper/modules';

const onSwiper = (swiper) => {
    // add logic if needed
};

const onSlideChange = () => {
    // add logic if needed
};

const testimonials = [
    { 
        name: 'John Doe', 
        comment: 'This product has transformed the way we work. Thanks to this innovative solution, our productivity has significantly increased. I highly recommend this company for its professionalism and commitment to its clients.', 
        role: 'CEO of TechCorp' 
    },
    { 
        name: 'Jane Smith', 
        comment: 'The team understood our specific needs and delivered a custom solution perfectly suited to our infrastructure. Their customer service is responsive and always available to assist us.', 
        role: 'CTO of Innovatech' 
    },
    { 
        name: 'Alice Johnson', 
        comment: 'Partnering with this company has been a real success. Their expertise and creativity allowed us to develop a digital solution that exceeds all our expectations. I am impressed by their quality of service.', 
        role: 'CEO of FutureTech' 
    },
    { 
        name: 'Michael Brown', 
        comment: 'The collaboration was smooth and efficient from start to finish. Thanks to their innovative approach, we were able to optimize our internal processes and gain a competitive edge in the market.', 
        role: 'Operations Director at NovaCorp' 
    },
    { 
        name: 'Sophie Martin', 
        comment: 'They turned a complex idea into an intuitive and high-performing application. Their attention to detail and commitment to quality are outstanding.', 
        role: 'Product Manager at DigitalWave' 
    },
    { 
        name: 'Daniel Lee', 
        comment: 'Flawless service, a competent team, and a technological solution that met our expectations. We are delighted with our collaboration.', 
        role: 'General Manager at AlphaSolutions' 
    }
];

</script>

<template>

    <section>

        <div class="container mx-auto px-4 animate-on-scroll">

            <!-- Section Header -->
            <SectionHeader>
                <template #subtitle>
                    Client Testimonials
                </template>
                <template #title>
                    What Our Clients Say
                </template>
                <template #description>
                    Hear from the clients we’ve partnered with and discover how our solutions have made a positive impact on their business.
                </template>
            </SectionHeader>


            <div class="relative overflow-hidden pt-3 py-10">
                <div class="absolute left-0 top-0 w-32 h-full bg-gradient-to-r from-white to-transparent z-10 hidden sm:block"></div>
                <div class="absolute right-0 top-0 w-32 h-full bg-gradient-to-l from-white to-transparent z-10 hidden sm:block"></div>
                <swiper
                    :modules="[Pagination]"
                    :slides-per-view="3"
                    :space-between="30"
                    :centered-slides="true"
                    :initial-slide="1"
                    :loop="true"
                    :pagination="{ clickable: true }"
                    :effect="'coverflow'"
                    :coverflowEffect="{
                        rotate: 0,
                        stretch: 0,
                        depth: 100,
                        modifier: 1,
                        slideShadows: false,
                    }"
                    :breakpoints="{
                        '320': {
                            slidesPerView: 1,
                            spaceBetween: 20
                        },
                        '768': {
                            slidesPerView: 2,
                            spaceBetween: 30
                        },
                        '1024': {
                            slidesPerView: 3,
                            spaceBetween: 30
                        }
                    }"
                    @swiper="onSwiper"
                    @slideChange="onSlideChange"
                    class="!overflow-visible"
                >
                    <swiper-slide v-for="(testimonial, index) in testimonials" :key="index" class="pb-8 transition-all duration-300 cursor-grab">
                        <div class="bg-gradient-to-br from-blue-50 border border-purple-300 to-purple-50 rounded-lg shadow-lg p-8 h-full flex flex-col transition-all duration-300">
                            <div class="mb-4 space-y-1">
                                <h4 class="text-lg font-semibold text-gray-700">{{ testimonial.name }}</h4>
                                <p class="text-indigo-600 text-xs">{{ testimonial.role }}</p>
                            </div>
                            <div class="flex-grow">
                                <p class="text-gray-600 italic mb-6 h-32">
                                    "{{ testimonial.comment }}"
                                </p>
                            </div>
                        </div>
                    </swiper-slide>
                </swiper>
            </div>

        </div>

    </section>

</template>

<style>

.swiper-pagination {
    top: calc(100% + 5px) !important;
}

@media (min-width: 767px) {
    .swiper-slide-active {
        transform: scale(1.05);
        z-index: 2;
    }

    .swiper-slide-prev,
    .swiper-slide-next {
        opacity: 0.7;
        transform: scale(0.9) translateY(20px);
    }
}

</style>