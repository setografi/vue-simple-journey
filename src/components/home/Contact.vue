<script setup></script>

<template>
  <section
    id="contact"
    class="bg-gradient-to-b from-neutral-600 to-neutral-500 text-white px-4 sm:px-8 md:px-12 lg:px-16 py-12 sm:py-16 md:py-20 lg:py-24"
  >
    <div class="max-w-7xl mx-auto px-3 sm:px-4 md:px-6">
      <h2
        class="text-3xl sm:text-4xl md:text-5xl mb-4 sm:mb-6 md:mb-8 lg:mb-10"
      >
        Ready to power your future<br class="hidden sm:block" />with sustainable
        energy?
      </h2>
      <p class="mb-10 sm:mb-16 md:mb-20 lg:mb-28">
        Fill out the form below and our experts respond in 24h.
      </p>

      <form
        class="grid grid-cols-1 md:grid-cols-3 gap-6 sm:gap-8 md:gap-10 max-w-6xl"
      >
        <div>
          <label class="block text-sm mb-1">First name *</label>
          <input
            type="text"
            class="w-full bg-transparent border-b border-white py-2 focus:outline-none focus:bg-neutral-600/20"
          />
        </div>
        <div>
          <label class="block text-sm mb-1">Last name *</label>
          <input
            type="text"
            class="w-full bg-transparent border-b border-white py-2 focus:outline-none focus:bg-neutral-600/20"
          />
        </div>
        <div>
          <label class="block text-sm mb-1">Email *</label>
          <input
            type="email"
            class="w-full bg-transparent border-b border-white py-2 focus:outline-none focus:bg-neutral-600/20"
          />
        </div>
        <div>
          <label class="block text-sm mb-1">Phone</label>
          <input
            type="tel"
            class="w-full bg-transparent border-b border-white py-2 focus:outline-none focus:bg-neutral-600/20"
          />
        </div>
        <div>
          <label class="block text-sm mb-1">Company / Organization name</label>
          <input
            type="text"
            class="w-full bg-transparent border-b border-white py-2 focus:outline-none focus:bg-neutral-600/20"
          />
        </div>
        <div>
          <label class="block text-sm mb-1">Location</label>
          <input
            type="text"
            class="w-full bg-transparent border-b border-white py-2 focus:outline-none focus:bg-neutral-600/20"
          />
        </div>
        <div class="md:col-span-3">
          <label class="block text-sm mb-1">How can we help</label>
          <textarea
            class="w-full bg-transparent border-b border-white py-2 focus:outline-none focus:bg-neutral-600/20"
            rows="3"
          ></textarea>
        </div>
        <div
          class="col-span-1 sm:col-span-2 md:col-start-2 md:col-span-1 flex justify-center mt-4 md:mt-6"
        >
          <button
            class="w-full max-w-xs md:max-w-full bg-teal-300 hover:bg-black text-black hover:text-white py-2 px-4 rounded-full transition-colors duration-300"
          >
            Contact Us
          </button>
        </div>
      </form>
    </div>
  </section>
</template>
