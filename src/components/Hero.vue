<script setup>
import videoSrc from '@/assets/img/sea.mp4';
</script>

<template>
  <section class="relative py-20 mb-4">
    <!-- Video Background -->
    <video
      autoplay
      muted
      loop
      playsinline
      class="absolute top-0 left-0 min-w-full h-full object-cover z-0"
    >
      <source :src="videoSrc" type="video/mp4" />
      Your browser does not support the video tag.
    </video>

    <!-- Overlay for better text readability -->
    <!-- <div class="absolute top-0 left-0 w-full h-full bg-blue-200 opacity-70 z-10"></div> -->
    
    <!-- Content -->
    <div
      class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col items-center z-20"
    >
      <div class="text-center">
        <h1
          class="text-4xl font-extrabold text-white sm:text-5xl md:text-6xl"
        >
          Become a Pirate
        </h1>
        <p class="my-4 text-xl font-bold text-white sm:text-clip md:text-2xl">
          Find a wide range of pirate jobs and opportunities
        </p>
      </div>
    </div>
  </section>
</template>