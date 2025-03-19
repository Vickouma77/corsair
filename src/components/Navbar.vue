<script setup lang="ts">
import logo from '@/assets/img/corsair.png';
</script>

<template>
    <nav class="bg-sky-500 boreder-b border-sky-700">
        <div class="mx-auto mx-w-7xl px-2 sm:px=6 lg:px-8">
            <div class="flex h-2o items-center justify-between">
                <div class="flex flex-1 items-center justify-center md:items-stretch md:justify-start">
                    <a class="flex flex-shrink-0 items-center mr-4" href="index.html">
                        <img class="h-10 w-auto" :src="logo" alt="corsair" />
                        <span class="hidden md:block text-white text-2xl font-bold ml-2">Corsair</span>
                    </a>
                    <div class="md:ml-auto">
                        <div class="flex space-x-2">
                            <a
                                href="index.html"
                                class="text-white bg-sky-900 hover:bg-gray-900 hover:text-white rounded-md px-3 py-2">
                                Home
                            </a>
                            <a
                                href="jobs.html"
                                class="text-white hover:bg-sky-900 hover:text-white rounded-md px-3 py-2"
                                >Jobs
                            </a>
                            <a
                                href="add-job.html"
                                class="text-white hover:bg-sky-900 hover:text-white rounded-md px-3 py-2"
                                >Add Job
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>