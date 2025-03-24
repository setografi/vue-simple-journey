<script setup>
import { ref, onMounted, onUnmounted, nextTick, computed } from "vue";
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

import ServiceCard from "../common/Card.vue";
import CardOne from "../../assets/card-1.webp";
import CardTwo from "../../assets/card-2.webp";
import CardThree from "../../assets/card-3.webp";

gsap.registerPlugin(ScrollTrigger);

const services = [
  {
    id: 1,
    title: "Infrastructure Solution",
    description:
      "Optimize your IT foundation with our cutting-edge infrastructure solutions. From cloud computing and data centers to network security and system integration, we ensure a scalable, secure, and high-performance IT environment tailored to your business needs.",
    image: CardOne,
    altText: "Infrastructure",
    bgColor: "bg-white",
  },
  {
    id: 2,
    title: "Digital Solution",
    description:
      "Drive innovation and efficiency with our digital transformation services. We provide custom software development, enterprise applications, automation, and AI-driven solutions to enhance productivity and customer experience in the digital era.",
    image: CardTwo,
    altText: "Digital Solution",
    bgColor: "bg-teal-300",
  },
  {
    id: 3,
    title: "Cross Industry Solution",
    description:
      "We deliver tailored technology solutions across industries, including finance, healthcare, retail, and manufacturing. Our expertise in industry-specific challenges allows us to create scalable, future-ready digital ecosystems that drive business growth.",
    image: CardThree,
    altText: "Cross Industry",
    bgColor: "bg-gray-200",
  },
  {
    id: 4,
    title: "IT Operation Services",
    description:
      "Ensure seamless IT operations with our end-to-end managed services. From IT support, cloud management, and cybersecurity to proactive monitoring and disaster recovery, we help you maintain high availability, security, and operational efficiency—without the hassle.",
    image: CardThree,
    altText: "IT Operations",
    bgColor: "bg-orange-100",
  },
];

const servicesSection = ref(null);
const cardsContainer = ref(null);
const isMobile = ref(false);
const scrollTriggers = ref([]);

// Function to check if screen is mobile
const checkMobile = () => {
  isMobile.value = window.innerWidth < 768; // Consider mobile if width is less than 768px (md breakpoint)
};

// Function to setup animations
const setupScrollAnimations = () => {
  // Clear any existing ScrollTrigger instances
  if (scrollTriggers.value.length) {
    scrollTriggers.value.forEach((trigger) => trigger.kill());
    scrollTriggers.value = [];
  }

  // Skip animation setup if mobile
  if (isMobile.value) {
    servicesSection.value.style.minHeight = "auto";
    return;
  }

  const cards = gsap.utils.toArray(".service-card");
  const headerSection = document.querySelector(".services-header");
  const headerHeight = headerSection ? headerSection.offsetHeight : 200;
  const padding = 50;

  // Set min height for proper scrolling
  servicesSection.value.style.minHeight = `calc(${headerHeight}px + ${
    services.length * 100
  }vh + ${padding}px)`;

  // Setup animations for each card
  cards.forEach((card, index) => {
    gsap.set(card, {
      y: index * 5,
      zIndex: 50 + index,
    });

    // Add scroll animation
    const scrollAnimation = gsap.to(card, {
      scrollTrigger: {
        trigger: card,
        start: () => `top bottom-=100`,
        end: () => `top top+=40`,
        scrub: true,
        invalidateOnRefresh: true,
      },
      ease: "none",
    });

    // Add pin effect
    const pinEffect = ScrollTrigger.create({
      trigger: card,
      start: "top top",
      pin: true,
      pinSpacing: false,
      end: () => `bottom+=${window.innerHeight * 0.5} bottom`,
      endTrigger: servicesSection.value,
      invalidateOnRefresh: true,
    });

    scrollTriggers.value.push(scrollAnimation.scrollTrigger, pinEffect);
  });
};

// Handle window resize
const handleResize = () => {
  checkMobile();
  nextTick(() => {
    setupScrollAnimations();
  });
};

onMounted(() => {
  checkMobile();
  nextTick(() => {
    setupScrollAnimations();
    window.addEventListener("resize", handleResize);
  });
});

onUnmounted(() => {
  window.removeEventListener("resize", handleResize);
  // Kill all ScrollTriggers when component is unmounted
  if (scrollTriggers.value.length) {
    scrollTriggers.value.forEach((trigger) => trigger.kill());
  }
});
</script>

<template>
  <section
    ref="servicesSection"
    id="services"
    class="bg-gradient-to-r from-neutral-500 to-black py-12 md:py-16 lg:py-28"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="services-header">
        <h2
          class="text-3xl sm:text-4xl lg:text-5xl text-center text-white mb-4 sm:mb-6"
        >
          Explore Our Services
        </h2>
        <p
          class="text-center text-white text-sm sm:text-base mb-8 sm:mb-12 lg:mb-16 max-w-3xl mx-auto"
        >
          Describe the service and how customers or clients can benefit from it.
          This is the place to <br class="hidden sm:block" />
          add a short description with relevant details, like pricing, duration
          and how to book.
        </p>
      </div>

      <div ref="cardsContainer" class="cards-container">
        <div
          v-for="(service, index) in services"
          :key="service.id"
          class="service-card mb-6 md:mb-0"
        >
          <ServiceCard
            :title="service.title"
            :description="service.description"
            :image="service.image"
            :altText="service.altText"
            :bgColor="service.bgColor"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.cards-container {
  position: relative;
  width: 100%;
  overflow: visible;
}

/* Standard mobile layout with no special effects */
@media (max-width: 767px) {
  .service-card {
    position: static;
    margin-bottom: 1.5rem;
  }
}

/* Restore scroll animation for tablet and desktop */
@media (min-width: 768px) {
  .service-card {
    position: relative;
    will-change: transform;
    transform-origin: top center;
    width: 100%;
  }
}
</style>
