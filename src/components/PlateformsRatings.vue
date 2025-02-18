<script setup>

const plateformsRatings = ['trustpilot.png', 'google.png', 'github-stars.png', 'github-downloads.png', 'global-clutch.png', 'clutch-reviews.png'];

</script>

<template>

  <div class="relative container mx-auto px-4 flex items-center overflow-hidden pause-on-hover">
    <div class="absolute left-0 top-0 w-32 h-full bg-gradient-to-r from-white to-transparent z-10"></div>
    <div class="absolute right-0 top-0 w-32 h-full bg-gradient-to-l from-white to-transparent z-10"></div>
    <div
      v-for="value in [1, 2]"
      :key="value" 
      class="flex items-center min-w-[960px] sm:min-w-full moving-tip-animation"
    >
      <div v-for="(rate, index) in plateformsRatings" :key="index">
        <img :src="`/images/rates/${rate}`" :alt="`${rate}`">
      </div>
    </div>
  </div>

</template>

<style scoped>

.moving-tip-animation {
  animation: moving-tip 15s linear infinite;
}

.pause-on-hover:hover .moving-tip-animation {
  animation-play-state: paused;
}

@keyframes moving-tip {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-100%);
  }
}

</style>