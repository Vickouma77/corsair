<script setup lang="ts">
import { ref, computed } from 'vue';

const props = defineProps({
    job: {
        type: Object,
    }
});

const showFullDescription = ref(false);

const toggleFullDiscription = () => {
    showFullDescription.value = !showFullDescription.value;
}

const truncatedDescription = computed(() => {
    let description = props.job?.description;
    if (!showFullDescription.value) {
        description = description?.substring(0, 90) + '...';
    }
    return description;
})
</script>

<template>
    <div class="bg-white rounded-xl shadow-md relative">
        <div class="p-4">
            <div class="mb-6">
                <div class="text-gray-600 my-2">{{ job?.type }}</div>
                <h3 class="text-xl font-bold">{{ job?.title }}</h3>
            </div>

            <div class="mb-5">
                <div>{{ truncatedDescription }}</div>
                <button @click="toggleFullDiscription" class="text-blue-500 hover:text-blue-600 mb-5">
                    {{ showFullDescription ? 'Less' : 'More' }}
                </button>
            </div>

            <h3 class="text-blue-400 mb-2">{{ job?.treasure_reward }}</h3>

            <div class="border border-gray-100 mb-5"></div>

            <div class="flex flex-col lg:flex-row justify-between mb-4">
                <div class="text-orange-700 mb-3">
                    <i class="pi pi-map-maker text-orange-400"></i>
                    {{ job?.location }}
                </div>
                <a
                    :href="'/job/' + job?.id"
                    class="h-[36px] bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-lg text-center text-sm"
                >
                    Read More
                </a>
            </div>
        </div>
    </div>
</template>