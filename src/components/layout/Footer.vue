<script setup>
// Footer component
const footerLinks = [
  { name: "Linkedin", href: "#" },
  { name: "Facebook", href: "#" },
  { name: "Instagram", href: "#" },
  { name: "Accessibility statement", href: "#" },
  { name: "Privacy policy", href: "#" },
];

const addressLines = [
  "Office 8",
  "Jl. Senopati No. 8B Level",
  "18A Senayan, Kebayoran Baru,",
  "Jakarta Selatan 12190",
];

const contactInfo = ["info@mysite.com", "Tel: 123-456-7890"];
</script>

<template>
  <footer
    class="bg-teal-300 text-black px-4 sm:px-8 md:px-12 lg:px-16 py-8 sm:py-12 md:py-16"
  >
    <div class="max-w-7xl mx-auto px-2 sm:px-4 md:px-6">
      <div class="flex flex-col md:flex-row justify-between items-start mb-4">
        <div class="mb-6 md:mb-0">
          <h2 class="text-2xl sm:text-3xl font-bold tracking-wider">
            SimpleJourney ✦
          </h2>
        </div>

        <div
          class="flex flex-col sm:flex-row space-y-6 sm:space-y-0 sm:space-x-8 md:space-x-16 lg:space-x-28 w-full sm:w-auto"
        >
          <div class="flex flex-col items-start text-sm sm:text-base">
            <div
              v-for="(line, index) in addressLines"
              :key="`address-${index}`"
            >
              {{ line }}
            </div>
          </div>
          <div
            class="flex flex-col items-start sm:items-end text-sm sm:text-base"
          >
            <div v-for="(info, index) in contactInfo" :key="`contact-${index}`">
              {{ info }}
            </div>
          </div>
        </div>
      </div>

      <!-- Divider line -->
      <div class="border-t border-black mt-4 mb-6 sm:mb-8 md:mb-10"></div>

      <!-- Footer links -->
      <div
        class="w-full flex flex-col sm:flex-row justify-between text-sm sm:text-base gap-4 sm:gap-0"
      >
        <a
          v-for="(link, index) in footerLinks"
          :key="`link-${index}`"
          :href="link.href"
          class="hover:underline"
        >
          {{ link.name }}
        </a>
      </div>

      <!-- Copyright -->
      <div
        class="mt-8 sm:mt-12 md:mt-16 text-center sm:text-right text-sm sm:text-base"
      >
        © 2035 by Viento. Built on
        <a href="#" class="underline">Wix Studio</a>
      </div>
    </div>
  </footer>
</template>
