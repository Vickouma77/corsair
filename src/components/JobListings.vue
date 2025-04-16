<script setup lang="ts">
import jobData from '../jobs.json';
import { ref } from 'vue';
import JobListing from './JobListing.vue';

const jobs = ref(jobData);

defineProps({
    limit: {
        type: Number
    },
    showButton: {
        type: Boolean,
        default: false
    }
});
</script>

<template>
    <section class="bg-blue-50 px-4 py-10">
        <div class="container-xl lg:container m-auto">
            <h2 class="text-3xl font-bold text-blue-500 mb-6 text-center">
                Browse Jobs
            </h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <JobListing v-for="job in jobs.slice(0, limit || jobs.length)" :key="job.id" :job="job" />
            </div>
        </div>
    </section>
    <section v-if="showButton" class="m-auto max-w-lg my-10 px-6">
      <a
        href="/jobs"
        class="block bg-blue-600 text-white text-center py-4 px-6 rounded-xl hover:bg-blue-700"
        >View All Jobs</a
      >
    </section>
</template>