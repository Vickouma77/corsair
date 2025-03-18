<script setup lang="ts">
import { ref } from 'vue'
const navOpen = ref(false)
</script>

<template>
    <div>
        <!-- Mobile -->
        <div>
            <div>
                <button @click="navOpen = !navOpen; console.log(navOpen)">
                    <svg :class="navOpen ? 'hidden' : ''" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
                    </svg>
                    <svg :class="navOpen ? '' : 'hidden'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12" />
                    </svg>
                </button>
            </div>

            <nav :class="navOpen ? '' : 'hidden'">
                <a class="block" href="#">Logo</a>
                <a class="block" href="#">Home</a>
                <a class="block" href="#">About</a>
                <a class="block" href="#">Services</a>
                <a class="block" href="#">Contact</a>
            </nav>
        </div>
    </div>
</template>

<style scoped>
.hidden {
    display: none;
}
</style>