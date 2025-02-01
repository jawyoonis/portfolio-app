<!-- src/components/Contact.vue -->
<template>
  <section
    id="contact"
    class="py-16 bg-gradient-to-b from-gray-800 to-gray-900 text-center relative"
  >
    <!-- Optional: Semi-Transparent Overlay for Enhanced Text Clarity -->
    <div class="absolute inset-0 bg-black opacity-40 pointer-events-none"></div>

    <div class="relative z-10 container mx-auto px-4">
      <!-- Contact Section Header -->
      <h2 class="text-5xl font-extrabold mb-8 text-white animate-fadeIn">
        Contact Me
      </h2>
      <p class="text-lg md:text-xl mb-6 text-gray-300 max-w-xl mx-auto">
        Feel free to reach out to me for collaboration, inquiries, or opportunities. Let’s create something amazing together!
      </p>

      <!-- Contact Info -->
      <div class="mt-10 flex justify-center">
        <p class="text-lg font-semibold text-gray-200">
          <span class="inline-block px-6 py-3 bg-indigo-600 text-white rounded-lg shadow-md">
            Email:
            <a href="awyoonisj@gmail.com" class="text-indigo-300 hover:underline">
             awyoonisj@gmail.com
            </a>
          </span>
        </p>
      </div>

      <!-- Social Links -->
      <div class="flex justify-center space-x-8 mt-12">
        <!-- LinkedIn Icon -->
        <a
          href="https://www.linkedin.com/in/jawyoonis/"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="LinkedIn Profile"
          class="group flex items-center space-x-2 bg-indigo-600 text-white px-6 py-3 rounded-full shadow-md hover:bg-indigo-700 transition-transform hover:scale-105"
        >
          <IconWithAnimation :icon="faLinkedin" />
          <span class="text-sm font-medium">LinkedIn</span>
        </a>

        <!-- GitHub Icon -->
        <a
          href="https://github.com/jawyoonis?tab=repositories"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="GitHub Profile"
          class="group flex items-center space-x-2 bg-gray-800 text-white px-6 py-3 rounded-full shadow-md hover:bg-gray-900 transition-transform hover:scale-105"
        >
          <IconWithAnimation :icon="faGithub" />
          <span class="text-sm font-medium">GitHub</span>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import IconWithAnimation from "./IconWithAnimation.vue";
import { faLinkedin, faGithub } from "@fortawesome/free-brands-svg-icons";

export default {
  components: {
    IconWithAnimation,
  },
  data() {
    return {
      faLinkedin,
      faGithub,
    };
  },
};
</script>

<style scoped>
/* Fade-in animation for heading */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fadeIn {
  animation: fadeIn 1.5s ease-out forwards;
}

/* Subtle Hover Animations */
.group:hover .icon-animation {
  animation: pulse 1s infinite;
}

@keyframes pulse {
  0%,
  100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
}

/* Responsive Adjustments */
@media (max-width: 768px) {
  .text-5xl {
    font-size: 2.5rem;
  }
  .px-6 {
    padding-left: 1.5rem;
    padding-right: 1.5rem;
  }
  .py-3 {
    padding-top: 0.75rem;
    padding-bottom: 0.75rem;
  }
}
</style>
