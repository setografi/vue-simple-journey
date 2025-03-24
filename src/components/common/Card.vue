<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
  image: {
    type: String,
    required: true,
  },
  altText: {
    type: String,
    default: "Service Image",
  },
  bgColor: {
    type: String,
    default: "bg-white",
  },
});
</script>

<template>
  <div
    :class="[
      'min-h-[40vh] sm:min-h-[45vh] md:min-h-[50vh]',
      'flex',
      'flex-col',
      'md:flex-row',
      'items-center',
      bgColor,
    ]"
  >
    <div
      class="w-full md:w-2/3 px-4 sm:px-8 md:px-12 lg:px-20 py-8 sm:py-12 md:py-16"
    >
      <h3
        class="text-black text-2xl sm:text-3xl md:text-4xl lg:text-5xl mb-4 sm:mb-6 md:mb-8 lg:mb-10"
      >
        {{ title }}
      </h3>
      <p class="text-black text-sm sm:text-base mb-4">{{ description }}</p>
    </div>

    <div class="w-full md:w-1/3 flex justify-center py-6 md:py-0">
      <img
        :src="image"
        :alt="altText"
        class="w-40 h-40 sm:w-48 sm:h-48 md:w-56 md:h-56 lg:w-64 lg:h-64 object-contain"
      />
    </div>
  </div>
</template>
