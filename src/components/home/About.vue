<script setup>
import ServicesBg from "../../assets/services-bg.webp";
</script>

<template>
  <section
    id="about"
    class="relative w-full min-h-screen bg-black text-white py-12 sm:py-16 md:py-20"
  >
    <!-- Background Image -->
    <div class="absolute inset-0">
      <div class="h-full w-full">
        <img
          :src="ServicesBg"
          alt="Background Services"
          class="absolute inset-0 w-full h-full object-cover opacity-70"
        />
      </div>
    </div>

    <!-- Content -->
    <div
      class="relative max-w-7xl h-full mx-auto px-4 sm:px-6 flex flex-col md:flex-row-reverse items-center justify-center md:justify-between"
    >
      <div class="w-full md:w-1/2 text-left py-8 md:py-0">
        <h2 class="text-3xl sm:text-4xl md:text-5xl mb-6 sm:mb-8 md:mb-10">
          About us
        </h2>

        <div class="flex flex-col sm:flex-row">
          <span class="text-teal-300 text-2xl sm:text-3xl mb-4 sm:mb-0 sm:mr-8"
            >✦</span
          >

          <ul class="space-y-4 sm:space-y-6">
            <li class="flex items-start">
              <p class="text-base sm:text-lg leading-7">
                PT Simple Journey Indonesia is an IT consulting company and a
                provider of Infrastructure Solutions, Digital Solutions,
                Cross-Industry Solutions, and IT Operation Services.
              </p>
            </li>
            <li class="flex items-start">
              <p class="text-base sm:text-lg leading-7">
                We deliver IT solutions to businesses on a global scale by
                providing IT experts with flexible arrangements to help our
                clients adapt to the digital world.
              </p>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>
