<template>
  <header class="bg-white border-b border-gray-200 sticky top-0 z-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-20">
        <!-- Logo -->
        <router-link
          to="/"
          class="text-2xl font-semi-bold tracking-wider text-gray-800 hover:text-gray-600 transition-colors"
        >
          LEZADA
        </router-link>

        <!-- Navigation -->
        <nav class="hidden lg:flex items-center space-x-8">
          <router-link
            to="/"
            class="text-gray-600 hover:text-gray-900 transition-colors text-sm"
          >
            Home
          </router-link>

          <router-link
            to="/shop"
            class="text-gray-600 hover:text-gray-900 transition-colors text-sm"
          >
            Shop
          </router-link>

          <!-- Catalog with Dropdown -->
          <div
            class="relative"
            @mouseenter="showCatalogMenu = true"
            @mouseleave="showCatalogMenu = false"
          >
            <router-link
              to="/catalog"
              class="text-gray-600 hover:text-gray-900 transition-colors text-sm inline-flex items-center"
            >
              Catalog
              <span
                class="ml-1 px-1.5 py-0.5 bg-teal-400 text-white text-xs rounded"
                >SALE</span
              >
              <svg
                class="w-4 h-4 ml-1"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                />
              </svg>
            </router-link>

            <!-- Mega Menu -->
            <transition name="fade">
              <div
                v-show="showCatalogMenu"
                class="absolute left-1/2 -translate-x-1/2 top-full pt-4 w-screen max-w-5xl"
              >
                <div
                  class="bg-white border border-gray-200 shadow-lg rounded-lg p-8"
                >
                  <div class="grid grid-cols-4 gap-8">
                    <!-- Column 1: Popular -->
                    <div>
                      <h3 class="text-gray-800 font-medium mb-4">Popular</h3>
                      <ul class="space-y-3">
                        <li>
                          <router-link
                            to="/catalog/causal"
                            class="text-gray-600 hover:text-gray-900 text-sm flex items-center gap-2"
                          >
                            Causal
                            <span
                              class="px-1.5 py-0.5 bg-red-500 text-white text-xs rounded"
                              >NEW</span
                            >
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/exclusive"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Exclusive
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/aligori"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Aligori
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/churidar"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Churidar
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/shalwar"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Shalwar
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/jeans"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Jeans
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/dress"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Dress
                          </router-link>
                        </li>
                      </ul>
                    </div>

                    <!-- Column 2: Best Selling -->
                    <div>
                      <h3 class="text-gray-800 font-medium mb-4">
                        Best Selling
                      </h3>
                      <ul class="space-y-3">
                        <li>
                          <router-link
                            to="/catalog/sandals"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Sandals
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/bast-shoe"
                            class="text-gray-600 hover:text-gray-900 text-sm flex items-center gap-2"
                          >
                            Bast shoe
                            <span
                              class="px-1.5 py-0.5 bg-red-500 text-white text-xs rounded"
                              >New</span
                            >
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/blucher-shoe"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Blucher shoe
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/boat-shoe"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Boat shoe
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/brogan"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Brogan
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/chelsea-boot"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Chelsea boot
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/brothel-creeper"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Brothel creeper
                          </router-link>
                        </li>
                      </ul>
                    </div>

                    <!-- Column 3: New Product -->
                    <div>
                      <h3 class="text-gray-800 font-medium mb-4">
                        New Product
                      </h3>
                      <ul class="space-y-3">
                        <li>
                          <router-link
                            to="/catalog/belt"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Belt
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/wallets"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Wallets
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/card-holders"
                            class="text-gray-600 hover:text-gray-900 text-sm flex items-center gap-2"
                          >
                            Card Holders
                            <span
                              class="px-1.5 py-0.5 bg-teal-400 text-white text-xs rounded"
                              >SALE</span
                            >
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/bags"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Bags
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/executive-bag"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Executive bag
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/cufflinks"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Cufflinks
                          </router-link>
                        </li>
                        <li>
                          <router-link
                            to="/catalog/cap"
                            class="text-gray-600 hover:text-gray-900 text-sm"
                          >
                            Cap
                          </router-link>
                        </li>
                      </ul>
                    </div>

                    <!-- Column 4: Product Image -->
                    <div>
                      <div class="bg-gray-50 rounded-lg p-6 text-center">
                        <div
                          class="w-32 h-32 md:w-55 md:h-55 mx-auto bg-white rounded-lg flex items-center justify-center mb-4"
                        >
                          <img
                            src="https://lezada-demo.myshopify.com/cdn/shop/products/per1_360x.jpg?v=1551249474"
                            alt="Organic Moon Fruit"
                            class="w-full h-full object-contain"
                          />
                        </div>
                        <h4 class="text-gray-800 text-sm font-medium mb-2">
                          Organic Moon Fruit
                        </h4>
                        <div class="flex items-center justify-center gap-2">
                          <span class="text-gray-900 font-semibold"
                            >$39.00</span
                          >
                          <span class="text-gray-400 line-through text-sm"
                            >$69.00</span
                          >
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </transition>
          </div>

          <div class="relative">
            <router-link
              to="/blog"
              class="text-gray-600 hover:text-gray-900 transition-colors text-sm inline-flex items-center"
            >
              Blog
              <svg
                class="w-4 h-4 ml-1"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                />
              </svg>
            </router-link>
          </div>

          <div class="relative">
            <router-link
              to="/pages"
              class="text-gray-600 hover:text-gray-900 transition-colors text-sm inline-flex items-center"
            >
              Pages
              <svg
                class="w-4 h-4 ml-1"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M19 9l-7 7-7-7"
                />
              </svg>
            </router-link>
          </div>
        </nav>

        <!-- Right Icons -->
        <div class="flex items-center space-x-4">
          <!-- Search -->
          <button class="text-gray-600 hover:text-gray-900 transition-colors">
            <svg
              class="w-5 h-5"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
              />
            </svg>
          </button>

          <!-- User -->
          <router-link
            to="/account"
            class="text-gray-600 hover:text-gray-900 transition-colors"
          >
            <svg
              class="w-5 h-5"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"
              />
            </svg>
          </router-link>

          <!-- Wishlist -->
          <router-link
            to="/wishlist"
            class="text-gray-600 hover:text-gray-900 transition-colors"
          >
            <svg
              class="w-5 h-5"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"
              />
            </svg>
          </router-link>

          <!-- Cart -->
          <router-link
            to="/cart"
            class="relative text-gray-600 hover:text-gray-900 transition-colors"
          >
            <svg
              class="w-5 h-5"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"
              />
            </svg>
            <span
              class="absolute -top-2 -right-2 bg-red-500 text-white text-xs rounded-full w-5 h-5 flex items-center justify-center"
            >
              0
            </span>
          </router-link>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";

const showCatalogMenu = ref(false);
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
