<template>
  <div class="relative w-full h-[500px] overflow-hidden bg-gray-100">
    <!-- Slides Container -->
    <div
      class="flex transition-transform duration-500 ease-in-out h-full"
      :style="{ transform: `translateX(-${currentSlide * 100}%)` }"
    >
      <!-- Slide 1 -->
      <div class="min-w-full h-full flex items-center justify-center relative">
        <div
          class="absolute inset-0 bg-gradient-to-r from-blue-50/90 to-blue-100/90"
        ></div>
        <div
          class="max-w-7xl mx-auto px-8 w-full grid grid-cols-2 gap-12 items-center relative z-10"
        >
          <!-- Left Content -->
          <div class="space-y-6">
            <p
              class="text-blue-500 text-sm font-semibold tracking-wider uppercase"
            >
              ACCESSORIES
            </p>
            <h2 class="text-5xl font-bold text-gray-800 leading-tight">
              Bottle Grinder,<br />
              Small, 2-Piecehe
            </h2>
            <button
              class="bg-gray-800 text-white px-8 py-3 hover:bg-gray-700 transition-colors font-medium"
            >
              SHOP NOW
            </button>
          </div>

          <!-- Right Image -->
          <div class="flex items-center justify-center">
            <img
              src="https://lezada-demo.myshopify.com/cdn/shop/files/banner-carousel-1_900x.jpg?v=1613746686"
              alt="Bottle Grinder"
              class="max-w-full h-auto"
            />
          </div>
        </div>

        <!-- Large Background Text -->
        <div
          class="absolute inset-0 flex items-center justify-center pointer-events-none opacity-5"
        >
          <p class="text-9xl font-black text-gray-800">ACCESSORIES</p>
        </div>
      </div>

      <!-- Slide 2 -->
      <div class="min-w-full h-full flex items-center justify-center relative">
        <div
          class="absolute inset-0 bg-gradient-to-r from-pink-50/90 to-pink-100/90"
        ></div>
        <div
          class="max-w-7xl mx-auto px-8 w-full grid grid-cols-2 gap-12 items-center relative z-10"
        >
          <!-- Left Content -->
          <div class="space-y-6">
            <p
              class="text-pink-500 text-sm font-semibold tracking-wider uppercase"
            >
              NEW COLLECTION
            </p>
            <h2 class="text-5xl font-bold text-gray-800 leading-tight">
              Modern Design<br />
              Living Room Set
            </h2>
            <button
              class="bg-gray-800 text-white px-8 py-3 hover:bg-gray-700 transition-colors font-medium"
            >
              SHOP NOW
            </button>
          </div>

          <!-- Right Image -->
          <div class="flex items-center justify-center">
            <img
              src="https://lezada-demo.myshopify.com/cdn/shop/files/banner-carousel-2_900x.jpg?v=1613746686"
              alt="Living Room Set"
              class="max-w-full h-auto"
            />
          </div>
        </div>

        <!-- Large Background Text -->
        <div
          class="absolute inset-0 flex items-center justify-center pointer-events-none opacity-5"
        >
          <p class="text-9xl font-black text-gray-800">FURNITURE</p>
        </div>
      </div>

      <!-- Slide 3 -->
      <div class="min-w-full h-full flex items-center justify-center relative">
        <div
          class="absolute inset-0 bg-gradient-to-r from-green-50/90 to-green-100/90"
        ></div>
        <div
          class="max-w-7xl mx-auto px-8 w-full grid grid-cols-2 gap-12 items-center relative z-10"
        >
          <!-- Left Content -->
          <div class="space-y-6">
            <p
              class="text-green-500 text-sm font-semibold tracking-wider uppercase"
            >
              KITCHEN ESSENTIALS
            </p>
            <h2 class="text-5xl font-bold text-gray-800 leading-tight">
              Premium Quality<br />
              Cookware Collection
            </h2>
            <button
              class="bg-gray-800 text-white px-8 py-3 hover:bg-gray-700 transition-colors font-medium"
            >
              SHOP NOW
            </button>
          </div>

          <!-- Right Image -->
          <div class="flex items-center justify-center">
            <img
              src="https://lezada-demo.myshopify.com/cdn/shop/files/banner-carousel-3_900x.jpg?v=1613746686"
              alt="Cookware"
              class="max-w-full h-auto"
            />
          </div>
        </div>

        <!-- Large Background Text -->
        <div
          class="absolute inset-0 flex items-center justify-center pointer-events-none opacity-5"
        >
          <p class="text-9xl font-black text-gray-800">KITCHEN</p>
        </div>
      </div>
    </div>

    <!-- Previous Button -->
    <button
      @click="previousSlide"
      class="absolute left-4 top-1/2 -translate-y-1/2 w-12 h-12 flex items-center justify-center text-gray-400 hover:text-gray-600 transition-colors z-20"
    >
      <svg
        class="w-8 h-8"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M15 19l-7-7 7-7"
        />
      </svg>
    </button>

    <!-- Next Button -->
    <button
      @click="nextSlide"
      class="absolute right-4 top-1/2 -translate-y-1/2 w-12 h-12 flex items-center justify-center text-gray-400 hover:text-gray-600 transition-colors z-20"
    >
      <svg
        class="w-8 h-8"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M9 5l7 7-7 7"
        />
      </svg>
    </button>

    <!-- Dots Indicator -->
    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 flex gap-2 z-20">
      <button
        v-for="(slide, index) in 3"
        :key="index"
        @click="currentSlide = index"
        class="w-2 h-2 rounded-full transition-all"
        :class="currentSlide === index ? 'bg-gray-800 w-8' : 'bg-gray-400'"
      ></button>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const currentSlide = ref(0);
let autoPlayInterval = null;

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % 3;
};

const previousSlide = () => {
  currentSlide.value = currentSlide.value === 0 ? 2 : currentSlide.value - 1;
};

const startAutoPlay = () => {
  autoPlayInterval = setInterval(() => {
    nextSlide();
  }, 5000);
};

const stopAutoPlay = () => {
  if (autoPlayInterval) {
    clearInterval(autoPlayInterval);
  }
};

onMounted(() => {
  startAutoPlay();
});

onUnmounted(() => {
  stopAutoPlay();
});
</script>
