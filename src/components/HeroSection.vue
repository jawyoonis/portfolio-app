<!-- src/components/HeroSection.vue -->
<template>
  <section
    class="min-h-screen bg-gradient-to-b from-indigo-700 via-purple-700 to-pink-600 flex flex-col justify-center items-center text-white text-center relative overflow-hidden"
  >
    <!-- Subtle Animated Background Overlay -->
    <div class="absolute inset-0 bg-gradient-to-tr from-indigo-600 via-purple-600 to-pink-500 opacity-30 animate-gradient-flow pointer-events-none"></div>

    <!-- Dark Overlay for Enhanced Readability -->
    <div class="absolute inset-0 bg-black opacity-40 pointer-events-none"></div>

    <!-- Floating Decorative Elements -->
    <div class="absolute top-12 left-16 w-24 h-24 rounded-full bg-yellow-300 opacity-80 shadow-lg transform animate-floatingBall"></div>
    <div class="absolute bottom-16 right-20 w-20 h-20 rounded-full bg-blue-300 opacity-60 shadow-lg transform animate-floatingBall delay-300"></div>

    <div class="relative z-10 px-4">
      <!-- Animated Avatar -->
      <AnimatedAvatar
        animationPath="https://assets5.lottiefiles.com/packages/lf20_2ldpnhxe.json"
        class="w-40 h-40 mb-6 mx-auto"
      />

      <!-- Introduction -->
      <h1 class="text-5xl md:text-6xl font-extrabold mt-6 animate-slideUp">
        Hi, I'm <span class="text-yellow-300">Jamal</span>
      </h1>
      <p class="text-lg md:text-xl mt-4 leading-relaxed animate-slideUp delay-200 max-w-2xl mx-auto">
        A <span class="font-bold text-blue-200">Passionate Engineer</span> who loves <span class="italic text-yellow-300">soccer</span> and <span class="italic text-blue-300">coding</span>. Let's create something
        amazing together.
      </p>

      <!-- Call to Action -->
      <div class="text-center mt-16 md:mt-20 lg:mt-24">
        <a
          href="#projects"
          class="bg-yellow-400 text-blue-900 py-4 px-8 rounded-full font-bold hover:bg-yellow-300 transform hover:scale-110 shadow-lg transition duration-300 ease-in-out animate-bounce"
        >
          View My Work
        </a>
      </div>
    </div>

    <!-- Footer Icon Animation -->
    <div class="absolute bottom-8 flex space-x-6">
      <a
        href="https://github.com/jawyoonis"
        target="_blank"
        rel="noopener noreferrer"
        class="w-12 h-12 bg-teal-700 rounded-full shadow-lg transform hover:scale-110 transition duration-300 ease-in-out animate-hoverIcon flex justify-center items-center"
      >
        <img
          src="https://cdn-icons-png.flaticon.com/512/2111/2111425.png"
          alt="GitHub Icon"
          class="w-8 h-8"
        />
      </a>
      <a
        href="https://linkedin.com/in/jawyoonis"
        target="_blank"
        rel="noopener noreferrer"
        class="w-12 h-12 bg-teal-700 rounded-full shadow-lg transform hover:scale-110 transition duration-300 ease-in-out animate-hoverIcon delay-300 flex justify-center items-center"
      >
        <img
          src="https://cdn-icons-png.flaticon.com/512/174/174857.png"
          alt="LinkedIn Icon"
          class="w-8 h-8"
        />
      </a>
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
/* Animation for background gradient */
@keyframes gradient-flow {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.animate-gradient-flow {
  background-size: 200% 200%;
  animation: gradient-flow 8s infinite;
}

/* Animation for slide-up text */
@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-slideUp {
  animation: slideUp 1.5s ease-out forwards;
}

/* Animation for bouncing Call-to-Action */
@keyframes bounce {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.animate-bounce {
  animation: bounce 2s infinite;
}

/* Animation for hovering icons */
@keyframes hoverIcon {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.animate-hoverIcon {
  animation: hoverIcon 3s infinite;
}

/* Animation for floating decorative elements */
@keyframes floatingBall {
  0%,
  100% {
    transform: translateY(0) scale(1);
  }
  50% {
    transform: translateY(-15px) scale(1.1);
  }
}

.animate-floatingBall {
  animation: floatingBall 4s infinite ease-in-out;
}

/* Styling for call-to-action button */
a {
  box-shadow: 0px 6px 15px rgba(0, 0, 0, 0.25);
}

/* Responsive Adjustments */
@media (max-width: 768px) {
  .text-6xl {
    font-size: 4xl;
  }
  .w-40 {
    width: 32;
    height: 32;
  }
  .w-12 {
    width: 10;
    height: 10;
  }
  .h-12 {
    height: 10;
  }
}
</style>
