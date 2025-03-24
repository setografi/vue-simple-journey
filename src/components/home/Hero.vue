<script setup></script>

<template>
  <section class="relative w-full h-screen bg-black text-white">
    <div class="absolute inset-0">
      <img
        src="https://static.wixstatic.com/media/11062b_3de8fc4100e6414ab42592cd0d6fe4cbf000.jpg/v1/fill/w_1024,h_673,al_c,q_85,usm_0.33_1.00_0.00,enc_avif,quality_auto/11062b_3de8fc4100e6414ab42592cd0d6fe4cbf000.jpg"
        alt="Background Hero"
        class="w-full h-full object-cover bg-center"
        style="object-position: 50% 50%"
        fetchpriority="high"
      />
    </div>

    <div class="relative h-full flex flex-row items-center justify-start">
      <div
        class="bg-black/70 w-full sm:w-4/5 md:w-3/5 lg:w-[35rem] flex flex-col items-start justify-center h-full px-4 sm:px-6 md:px-8 lg:px-10 pt-6 sm:pt-8 lg:pt-10"
      >
        <h1
          class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl mb-2 sm:mb-3 md:mb-4 leading-tight"
        >
          Your IT<br />
          Transformation<br />
          Partner
        </h1>
        <p
          class="text-base sm:text-lg text-white mb-8 sm:mb-10 md:mb-12 lg:mb-16"
        >
          Empowering Businesses with Smart IT<br />
          Solutions for a Digital Future
        </p>
        <button
          class="bg-teal-300 hover:bg-orange-100 text-black px-6 sm:px-8 py-3 sm:py-4 rounded-full shadow-lg transition duration-300"
        >
          Learn more
        </button>
      </div>
    </div>
  </section>
</template>
