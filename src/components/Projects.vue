<!-- src/components/Projects.vue -->
<template>
  <section id="projects" class="py-16 bg-gradient-to-b from-gray-800 to-gray-900 text-center relative">
    <!-- Optional: Semi-Transparent Overlay for Text Clarity -->
    <div class="absolute inset-0 bg-black opacity-30 pointer-events-none"></div>

    <div class="relative z-10 container mx-auto px-4">
      <!-- Projects Section Header -->
      <h2 class="text-4xl font-extrabold mb-12 text-white animate-fadeIn">
        My Projects
      </h2>

      <!-- Interactive Slider -->
      <div class="relative overflow-hidden">
        <div
          class="flex space-x-8 transition-transform duration-500"
          :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
          ref="slider"
        >
          <div
            v-for="project in projects"
            :key="project.id"
            class="w-full md:w-1/3 lg:w-1/4 p-6 bg-gray-800 shadow-md rounded-lg hover:shadow-xl transform hover:scale-105 transition duration-300 relative"
          >
            <!-- Decorative Background Animation -->
            <div
              class="absolute inset-0 bg-gradient-to-tr from-gray-700 via-indigo-700 to-purple-700 opacity-20 transform scale-150 -z-10 rounded-lg"
            ></div>

            <!-- Project Icon -->
            <div
              class="flex justify-center items-center bg-indigo-700 text-white rounded-full w-16 h-16 mb-4 mx-auto shadow-md animate-icon"
            >
              <font-awesome-icon :icon="project.icon" class="text-2xl" />
            </div>

            <!-- Project Title -->
            <h3 class="text-lg font-semibold mb-2 text-center text-white">
              {{ project.title }}
            </h3>

            <!-- Description -->
            <p class="text-sm text-gray-300 mb-4 text-center">
              {{ project.description }}
            </p>

            <!-- Tags -->
            <div class="flex flex-wrap justify-center mb-4">
              <span
                v-for="tag in project.tags"
                :key="tag"
                class="text-xs bg-indigo-600 text-white px-2 py-1 rounded-full m-1"
              >
                {{ tag }}
              </span>
            </div>

            <!-- View Project Button -->
            <div class="text-center mt-4">
              <a
                :href="project.link"
                class="bg-indigo-600 text-white py-2 px-4 rounded-lg hover:bg-indigo-500 transition duration-300"
                target="_blank"
                rel="noopener noreferrer"
                aria-label="View Project"
              >
                View Project
              </a>
            </div>
          </div>
        </div>

        <!-- Navigation Buttons -->
        <div class="absolute inset-x-0 flex justify-between items-center top-1/2 transform -translate-y-1/2 px-4">
          <button
            class="bg-gray-700 hover:bg-gray-600 text-white w-10 h-10 rounded-full flex justify-center items-center shadow-md disabled:opacity-50 disabled:cursor-not-allowed transition duration-300 ease-in-out"
            @click="prevSlide"
            :disabled="currentIndex === 0"
            aria-label="Previous Slide"
          >
            <span>&larr;</span>
          </button>
          <button
            class="bg-gray-700 hover:bg-gray-600 text-white w-10 h-10 rounded-full flex justify-center items-center shadow-md disabled:opacity-50 disabled:cursor-not-allowed transition duration-300 ease-in-out"
            @click="nextSlide"
            :disabled="currentIndex === projects.length - 1"
            aria-label="Next Slide"
          >
            <span>&rarr;</span>
          </button>
        </div>
      </div>
    </div>

    <!-- Import Technologies Section -->
    <Technologies />
  </section>
</template>

<script>
import Technologies from "./Technologies.vue";
import {
  faFileCode,
  faCar,
  faSchool,
  faHeartbeat,
  faCodeBranch,
} from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

export default {
  components: {
    FontAwesomeIcon,
    Technologies,
  },
  data() {
    return {
      currentIndex: 0,
      projects: [
        {
          id: 1,
          title: "Tax Business Management Platform",
          description:
            "A scalable platform for file uploads, tracking, and scheduling.",
          tags: ["Vue.js", "Spring Boot", "MySQL", "Docker"],
          link: "https://github.com/jawyoonis/tax-solutions-application",
          icon: faFileCode,
        },
        {
          id: 2,
          title: "NEMT Business Platform",
          description: "A transportation platform for scheduling and tracking.",
          tags: ["Vue.js", "Spring Boot", "Kubernetes"],
          link: "https://example.com/project-2",
          icon: faCar,
        },
        {
          id: 3,
          title: "Registrar Office Automation System",
          description:
            "Streamlining professor assignments and room allocations.",
          tags: ["Python", "Flask", "Bootstrap", "Docker", "MySQL", "JINJA"],
          link: "https://github.com/BCStudentSoftwareDevTeam/cas/tree/development",
          icon: faSchool,
        },
        {
          id: 4,
          title: "Healthcare Management System",
          description:
            "HR and clock-in systems for employees visiting clients.",
          tags: ["Java", "Spring Boot", "Vue.js"],
          link: "https://github.com/jawyoonis/HealthClaimPro-EDI-837P-Processing-System",
          icon: faHeartbeat,
        },
        {
          id: 5,
          title: "Open Source Contribution to Firefox",
          description:
            "Resolved bugs and added features to enhance browser performance.",
          tags: ["JavaScript", "Bug Fixing", "Open Source"],
          link: "https://github.com/firefox-devtools/debugger/pull/6026",
          icon: faCodeBranch,
        },
      ],
    };
  },
  methods: {
    nextSlide() {
      if (this.currentIndex < this.projects.length - 1) {
        this.currentIndex++;
      }
    },
    prevSlide() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      }
    },
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

/* Animation for fade-in header */
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

/* Animation for project icons */
@keyframes iconPulse {
  0%,
  100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
}

.animate-icon {
  animation: iconPulse 3s infinite;
}

/* Responsive Adjustments */
@media (max-width: 768px) {
  .text-4xl {
    font-size: 2rem;
  }
  .w-16 {
    width: 4rem;
    height: 4rem;
  }
  .w-10,
  .h-10,
  .w-12,
  .h-12 {
    width: 2.5rem;
    height: 2.5rem;
  }
  .w-6,
  .h-6 {
    width: 1.5rem;
    height: 1.5rem;
  }
}

/* Styling for navigation buttons */
button:disabled {
  cursor: not-allowed;
}
</style>
