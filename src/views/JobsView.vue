<script setup lang="ts">
import { ref, onMounted } from 'vue';
import { useRoute, RouterLink } from 'vue-router';
import axios from 'axios';
import BackButton from '@/components/BackButton.vue';

const route = useRoute();
const jobId = route.params.id;

interface Job {
    id?: number;
    type?: string;
    title?: string;
    location?: string;
    description?: string;
    treasure_reward?: string;
    ship_name?: string;
    ship_info?: string;
    contact?: string;
}

const job = ref<Job>({});
onMounted(async () => {
    try {
        const response = await axios.get(`http://localhost:8000/jobs/${jobId}`);
        job.value = response.data;
    } catch (error) {
        console.error('Error fetching jobs:', error);
    }
});
</script>

<template>
  <BackButton />
    <section class="bg-green-50">
      <div class="container m-auto py-10 px-6">
        <div class="grid grid-cols-1 md:grid-cols-70/30 w-full gap-6">
          <main>
            <div
              class="bg-white p-6 rounded-lg shadow-md text-center md:text-left"
            >
              <div class="text-gray-500 mb-4">{{ job?.type }}</div>
              <h1 class="text-3xl font-bold mb-4">{{ job?.title }}</h1>
              <div
                class="text-gray-500 mb-4 flex align-middle justify-center md:justify-start"
              >
                <i
                  class="fa-solid fa-location-dot text-lg text-orange-700 mr-2"
                ></i>
                <p class="text-orange-700">{{ job?.location }}</p>
              </div>
            </div>

            <div class="bg-white p-6 rounded-lg shadow-md mt-6">
              <h3 class="text-green-800 text-lg font-bold mb-6">
                Job Description
              </h3>

              <p class="mb-4">
                {{ job?.description }}.
              </p>

              <h3 class="text-green-800 text-lg font-bold mb-2">Salary</h3>

              <p class="mb-4">{{ job?.treasure_reward }}</p>
            </div>
          </main>

          <!-- Sidebar -->
          <aside>
            <!-- Company Info -->
            <div class="bg-white p-6 rounded-lg shadow-md">
              <h3 class="text-xl font-bold mb-6">Ship Name</h3>

              <h2 class="text-2xl">{{ job?.ship_name }}</h2>

              <p class="my-2">
                {{ job?.ship_info }}
              </p>

              <hr class="my-4" />

              <h3 class="text-xl">Contact Point:</h3>

              <p class="my-2 bg-green-100 p-2 font-bold">
                {{ job?.contact }}
              </p>
            </div>

            <!-- Manage -->
            <div class="bg-white p-6 rounded-lg shadow-md mt-6">
              <h3 class="text-xl font-bold mb-6">Manage Job</h3>
              <RouterLink
                :to="`/jobs/edit/${job?.id}`"
                class="bg-green-500 hover:bg-green-600 text-white text-center font-bold py-2 px-4 rounded-full w-full focus:outline-none focus:shadow-outline mt-4 block"
                >Edit Job</RouterLink
              >
              <button
                class="bg-red-500 hover:bg-red-600 text-white font-bold py-2 px-4 rounded-full w-full focus:outline-none focus:shadow-outline mt-4 block"
              >
                Delete Job
              </button>
            </div>
          </aside>
        </div>
      </div>
    </section>
</template>