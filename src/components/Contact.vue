<script setup>

import axios from 'axios';
import { ref } from 'vue';
import TextInput from './TextInput.vue';
import InputLabel from './InputLabel.vue';
import TextareaInput from './TextareaInput.vue';

axios.defaults.withCredentials = true;
axios.defaults.withXSRFToken = true;

const formData = ref({
  name: '',
  email: '',
  subject: '',
  content: ''
});

const formStatus = ref({
  loading: false,
  success: false,
  error: null
});

const handleSubmit = async () => {
  formStatus.value.loading = true;
  formStatus.value.error = null;
  
  try {
     /* const response = await axios.post('API endpoint', formData.value, {
      headers: {
        'Content-Type': 'application/json',
        'X-XSRF-TOKEN': csrfToken
      }
    });*/
    await new Promise(resolve => setTimeout(resolve, 5000));
    console.log(formData.value);
    formStatus.value.success = true;
    formData.value = { name: '', email: '', subject: '', content: '' };
    
    setTimeout(() => {
      formStatus.value.success = false;
    }, 3000);
  } catch (error) {
    console.error('API Error:', error);
    formStatus.value.error = 'Failed to send message. Please try again.';
  } finally {
    formStatus.value.loading = false;
  }
};

</script>

<template>

    <section>
        <div class="grid grid-cols-1 sm:grid-cols-2 animate-on-scroll">
            <div class="relative min-h-[750px] sm:min-h-fit">
                <div class="absolute top-0 left-0 w-full h-full bg-gradient-to-r from-blue-600 to-purple-600 opacity-95"></div>
                <img class="w-full h-full object-cover object-center" src="/images/contact.jpg" alt="contact image">
                <div class="absolute top-16 left-0 w-full h-full z-40 flex flex-col items-center gap-4 p-2 sm:p-8">
                    <h1 class="text-white font-bold text-6xl">Get in Touch</h1>
                    <p class="text-white font-bold text-center text-xl">
                        Have a question or ready to start your next project? Our team is here to help! Whether you’re looking for a custom web solution, innovative design, or digital strategy, we’re just a message away. Let’s collaborate to turn your ideas into reality and build something amazing together.
                    </p>
                    <img class="max-w-96 aspect-square" src="/images/contact-image.png" alt="contact image"/>
                </div>
            </div>
            <div class="flex flex-col gap-8 p-8">
                <h1 class="font-bold text-3xl w-fit mx-auto">Contact  Us</h1>
                <form @submit.prevent="handleSubmit" class="space-y-4">
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div class="space-y-2">
                            <InputLabel for="name">Name</InputLabel>
                            <TextInput id="name" v-model="formData.name" type="text" required placeholder="Please enter your name" />
                        </div>
                        <div class="space-y-2">
                            <InputLabel for="email">Email</InputLabel>
                            <TextInput id="email" v-model="formData.email" type="email" required placeholder="Please enter your professional email" />
                        </div>
                    </div>

                    <div class="space-y-2">
                        <InputLabel for="subject">Subject</InputLabel>
                        <TextInput id="subject" v-model="formData.subject" type="text" required placeholder="Please enter the subject of your message" />
                    </div>

                    <div class="space-y-2">
                        <InputLabel for="message">Message</InputLabel>
                        <TextareaInput id="message" v-model="formData.content" required rows="10" placeholder="Please tell us about your need" ></TextareaInput>
                    </div>

                    <div class="flex justify-between items-center gap-8">
                        <div>
                            <p v-if="formStatus.success" class="flex items-center text-green-600">
                                <i class="fa-solid fa-check-circle mr-2"></i>
                                Message sent successfully
                            </p>
                            
                            <p v-if="formStatus.error" class="flex items-center text-red-600">
                                <i class="fa-solid fa-exclamation-circle mr-2"></i>
                                {{ formStatus.error }}
                            </p>
                        </div>

                        <button :disabled="formStatus.loading" type="submit" 
                            class="inline-flex items-center px-6 py-3 border border-transparent font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500 disabled:opacity-50 disabled:cursor-not-allowed">
                            <span v-if="!formStatus.loading">Send</span>
                            <span v-else class="inline-flex items-center">
                                <i class="fa-solid fa-circle-notch fa-spin mr-2"></i>
                                Sending in progress...
                            </span>
                        </button>
                    </div>
                </form>
            </div>
        </div>
    </section>

</template>