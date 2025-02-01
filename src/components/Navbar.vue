<template>
  <nav
    class="bg-gradient-to-r from-blue-600/90 via-blue-700/90 to-indigo-800/90 backdrop-blur-md border-b border-white/10 text-white fixed w-full z-50 shadow-xl"
    :class="{ 'h-16': !isMobileMenuOpen, 'h-auto': isMobileMenuOpen }"
  >
    <div class="container mx-auto px-4 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <!-- Logo with hover animation -->
        <a
          href="#"
          class="flex items-center space-x-2 group"
          @click.prevent="scrollToSection('hero')"
        >
          <span
            class="text-2xl font-bold tracking-tighter bg-gradient-to-r from-cyan-400 to-blue-300 bg-clip-text text-transparent transition-all duration-300 group-hover:scale-105"
          >
            JAW
          </span>
          <span class="h-4 w-[1px] bg-white/40 rotate-12"></span>
          <span class="text-sm font-medium text-blue-100/90">Portfolio</span>
        </a>

        <!-- Desktop Navigation -->
        <div class="hidden md:flex items-center space-x-8">
          <button
            v-for="link in navigationLinks"
            :key="link.id"
            @click="scrollToSection(link.id)"
            class="relative px-3 py-1.5 font-medium text-sm hover:text-cyan-300 transition-colors"
            :class="{ 'text-cyan-400': activeSection === link.id }"
          >
            <span class="relative z-10">{{ link.label }}</span>
            <span
              v-if="activeSection === link.id"
              class="absolute inset-0 bg-white/10 rounded-lg"
            ></span>
          </button>
        </div>

        <!-- Mobile Menu Button -->
        <button
          @click="toggleMobileMenu"
          class="md:hidden p-2 rounded-lg hover:bg-white/10 transition-colors"
          aria-label="Toggle navigation menu"
        >
          <svg
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              :d="isMobileMenuOpen ? 'M6 18L18 6M6 6l12 12' : 'M4 6h16M4 12h16M4 18h16'"
            />
          </svg>
        </button>
      </div>

      <!-- Mobile Navigation -->
      <transition
        enter-active-class="transition ease-out duration-200"
        enter-from-class="opacity-0 translate-y-2"
        enter-to-class="opacity-100 translate-y-0"
        leave-active-class="transition ease-in duration-150"
        leave-from-class="opacity-100 translate-y-0"
        leave-to-class="opacity-0 translate-y-2"
      >
        <div
          v-if="isMobileMenuOpen"
          class="md:hidden pb-4 space-y-4"
        >
          <button
            v-for="link in navigationLinks"
            :key="link.id"
            @click="scrollToSection(link.id)"
            class="block w-full px-4 py-3 text-left rounded-lg hover:bg-white/10 transition-colors"
            :class="{ 'text-cyan-400': activeSection === link.id }"
          >
            {{ link.label }}
          </button>
        </div>
      </transition>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isMobileMenuOpen: false,
      activeSection: 'hero',
      navigationLinks: [
        { id: 'about', label: 'About' },
        { id: 'projects', label: 'Projects' },
        { id: 'contact', label: 'Contact' }
      ]
    };
  },
  methods: {
    scrollToSection(sectionId) {
      this.activeSection = sectionId;
      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth', block: 'start' });
        window.history.replaceState(null, null, `#${sectionId}`);
      }
      this.isMobileMenuOpen = false;
    },
    toggleMobileMenu() {
      this.isMobileMenuOpen = !this.isMobileMenuOpen;
    },
    handleScroll() {
      const sections = this.navigationLinks.map(link => document.getElementById(link.id));
      const scrollPosition = window.scrollY + 100;

      sections.forEach(section => {
        if (section) {
          const sectionTop = section.offsetTop;
          const sectionHeight = section.offsetHeight;
          if (scrollPosition >= sectionTop && scrollPosition < sectionTop + sectionHeight) {
            this.activeSection = section.id;
          }
        }
      });
    },
    handleResize() {
      if (window.innerWidth >= 768) {
        this.isMobileMenuOpen = false;
      }
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
    window.addEventListener('resize', this.handleResize);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
    window.removeEventListener('resize', this.handleResize);
  }
};
</script>

<style scoped>
nav {
  transition: background-color 0.3s ease, backdrop-filter 0.3s ease;
}

/* Custom scroll behavior for smooth section transitions */
html {
  scroll-behavior: smooth;
}

@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }
}
</style>