<script setup lang="ts">
import Footer from '../components/Footer.vue';
import HomeCards from '../components/HomeCards.vue';
import JobListings from '../components/JobListings.vue';
import Hero from '../components/Hero.vue';
</script>

<template>
    <Hero />
    <HomeCards />
    <JobListings :limit="3" :show-button="true" />
    <Footer />
</template>