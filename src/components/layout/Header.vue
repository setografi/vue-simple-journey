<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const isVisible = ref(false);
const isHidden = ref(false);
const isMenuOpen = ref(false);
let lastScrollY = window.scrollY;

const navLinks = [
  { name: "Home", href: "#" },
  { name: "Services", href: "#services" },
  { name: "About", href: "#about" },
  { name: "Contact Us", href: "#contact" },
];

const handleScroll = () => {
  const currentScrollY = window.scrollY;
  isVisible.value = currentScrollY > 50;
  isHidden.value = currentScrollY > lastScrollY;
  lastScrollY = currentScrollY;
};

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const closeMenu = () => {
  isMenuOpen.value = false;
};

onMounted(() => window.addEventListener("scroll", handleScroll));
onUnmounted(() => window.removeEventListener("scroll", handleScroll));
</script>

<template>
  <header
    :class="[
      'fixed top-0 left-0 right-0 z-[70] py-2 px-4 sm:py-3 sm:px-6 md:px-8 lg:px-10 transition-all duration-300',
      isVisible ? 'bg-black/40 backdrop-blur-md' : 'bg-transparent',
      isHidden ? '-translate-y-full' : 'translate-y-0',
    ]"
  >
    <nav class="max-w-7xl mx-auto flex justify-between items-center">
      <h1
        class="flex text-xl sm:text-2xl md:text-3xl font-bold text-white tracking-wider"
      >
        <span>SimpleJourney ✦</span>
      </h1>

      <!-- Mobile menu button -->
      <button
        @click="toggleMenu"
        class="lg:hidden text-white p-2 focus:outline-none"
        aria-label="Toggle menu"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            v-if="!isMenuOpen"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          />
          <path
            v-else
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </button>

      <!-- Desktop menu -->
      <div
        class="hidden lg:block bg-white/60 p-2 md:p-3 lg:p-4 rounded-full shadow-lg"
      >
        <ul class="flex items-center space-x-2 lg:space-x-4">
          <li v-for="link in navLinks" :key="link.href">
            <a
              :href="link.href"
              class="text-black text-base lg:text-lg px-4 sm:px-6 lg:px-8 py-1 sm:py-2 hover:bg-white transition-colors rounded-full"
            >
              {{ link.name }}
            </a>
          </li>
        </ul>
      </div>

      <!-- Mobile menu -->
      <div
        v-if="isMenuOpen"
        class="absolute top-full left-0 right-0 h-dvh bg-black lg:hidden py-4"
      >
        <ul class="flex flex-col items-center space-y-4">
          <li v-for="link in navLinks" :key="link.href" class="w-full">
            <a
              :href="link.href"
              @click="closeMenu"
              class="block text-white text-center text-lg px-6 py-2 hover:bg-white/10 transition-colors w-full"
            >
              {{ link.name }}
            </a>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>
