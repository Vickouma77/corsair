<script setup lang="ts">
import Card from '@/components/Card.vue';
</script>

<template>
    <!-- Crew and Captains -->
    <section class="py-4">
      <div class="container-xl lg:container m-auto">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 p-4 rounded-lg">

          <Card bg="bg-blue-100">
            <h2 class="text-2xl font-bold">For Crews</h2>
            <p class="mt-2 mb-4">
                Find the perfect job for you and start your adventure
            </p>
            <a
              href="jobs.html"
              class="inline-block bg-black text-white rounded-lg px-4 py-2 hover:bg-gray-700"
            >
              Browse Jobs
            </a>
          </Card>

          <Card bg="bg-blue-200">
            <h2 class="text-2xl font-bold">For Captains</h2>
            <p class="mt-2 mb-4">
                Post your job and find the perfect crew for your ship
            </p>
            <a
              href="add-job.html"
              class="inline-block bg-blue-500 text-white rounded-lg px-4 py-2 hover:bg-green-600"
            >
              Add Job
            </a>
        </Card>
        
        </div>
      </div>
    </section>
</template>