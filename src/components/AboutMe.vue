<!-- src/components/About.vue -->
<template>
  <section
    id="about"
    class="py-16 bg-gradient-to-b from-gray-800 to-gray-900 text-center relative"
  >
    <!-- Optional: Semi-Transparent Overlay for Text Clarity -->
    <div class="absolute inset-0 bg-black opacity-30 pointer-events-none"></div>

    <div class="relative z-10 max-w-6xl mx-auto px-4">
      <!-- Section Header -->
      <h2 class="text-4xl font-extrabold mb-8 text-white animate-fadeIn">
        About Me
      </h2>

      <!-- Content Layout -->
      <div
        class="flex flex-col lg:flex-row items-center lg:items-start lg:space-x-12 animate-slideContent"
      >
        <!-- Animated Avatar -->
        <div
          class="mb-8 lg:mb-0 lg:w-1/3 transform hover:scale-105 transition duration-300"
        >
          <AnimatedAvatar
            animationPath="https://assets10.lottiefiles.com/packages/lf20_vwsaxyem.json"
            class="w-48 h-48 mx-auto"
          />
        </div>

        <!-- Interactive Content -->
        <div
          class="lg:w-2/3 text-lg text-gray-200 leading-relaxed space-y-4 bg-gray-800 p-6 rounded-lg shadow-md hover:shadow-lg transform hover:-translate-y-1 transition duration-300"
        >
          <p>
            Hi there! I'm
            <span
              class="font-bold text-blue-400 hover:text-indigo-400 transition-colors duration-300"
              >Jamal Awyonis</span
            >,
            a
            <span class="underline decoration-yellow-300 decoration-2">creative</span>
            and <span class="italic">dedicated</span> software engineer. My passion lies in
            building
            <span
              class="font-semibold text-blue-400 hover:text-yellow-300 transition-colors duration-300"
              >scalable</span
            >
            and
            <span
              class="font-semibold text-indigo-400 hover:text-yellow-300 transition-colors duration-300"
              >efficient</span
            >
            platforms that solve real-world problems.
          </p>
          <p class="hover:translate-x-1 transition-transform duration-300">
            With expertise in
            <span class="font-semibold text-blue-400">system integrations</span>,
            <span class="font-semibold text-blue-400">automation</span>, and
            <span class="font-semibold text-blue-400">cloud computing</span>, I’ve
            delivered solutions for various industries, ensuring
            <span class="underline decoration-indigo-300 decoration-2">reliability</span>
            and
            <span class="underline decoration-indigo-300 decoration-2">cost-effectiveness</span>.
          </p>
          <p class="hover:translate-y-1 transition-transform duration-300">
            Currently pursuing my
            <span class="font-bold text-indigo-400">Master's in Data Science</span>
            at
            <span class="font-bold text-indigo-400">Georgia Institute of Technology</span>,
            I’m honing skills in
            <span class="text-blue-400">AI</span>,
            <span class="text-blue-400">machine learning</span>, and
            <span class="text-blue-400">data analytics</span>.
          </p>
          <p>
            I believe in blending
            <span class="italic text-indigo-400">innovation</span> with
            <span class="italic text-yellow-300">functionality</span> to create
            technology that makes a difference.
          </p>
        </div>
      </div>

      <!-- Animated Call to Action -->
      <div class="mt-12">
        <a
          href="#contact"
          class="inline-block bg-blue-600 text-white py-3 px-8 rounded-lg font-semibold hover:bg-indigo-600 transform hover:scale-105 transition duration-300 shadow-md"
        >
          Get in Touch
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import AnimatedAvatar from "./AnimatedAvatar.vue";

export default {
  components: {
    AnimatedAvatar,
  },
};
</script>

<style scoped>
/* Fade-in animation for heading */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fadeIn {
  animation: fadeIn 1.5s ease-out;
}

/* Sliding animation for content */
@keyframes slideContent {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.animate-slideContent {
  animation: slideContent 1.5s ease-out;
}

/* Bouncing animation for button (removed for subtlety) */
/*
@keyframes bounce {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.animate-bounce {
  animation: bounce 2s infinite;
}
*/

/* Styling for call-to-action button */
a {
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
}

/* Responsive Adjustments */
@media (max-width: 768px) {
  .text-6xl {
    font-size: 3xl;
  }
  .w-48 {
    width: 12rem;
    height: 12rem;
  }
  .w-10,
  .h-10 {
    width: 10;
    height: 10;
  }
  .w-6,
  .h-6 {
    width: 6;
    height: 6;
  }
}
</style>
