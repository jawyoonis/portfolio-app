<template>
    <section
      id="technologies"
      class="py-16 bg-gradient-to-b from-blue-50 to-blue-100 text-center"
    >
      <div class="container mx-auto px-4">
        <!-- Section Title -->
        <h2 class="text-5xl font-extrabold text-blue-800 mb-12">
          Technologies
        </h2>
  
        <!-- Categories -->
        <div class="space-y-16">
          <div v-for="category in categorizedTechnologies" :key="category.title">
            <!-- Category Title -->
            <h3 class="text-3xl font-semibold text-teal-600 mb-8">
              {{ category.title }}
            </h3>
  
            <!-- Technology Grid -->
            <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-8">
              <div
                v-for="tech in category.technologies"
                :key="tech.name"
                class="relative bg-white shadow-lg rounded-xl p-6 flex flex-col items-center transform hover:scale-110 hover:shadow-2xl transition duration-300"
              >
                <!-- Circular Progress Bar -->
                <div class="relative w-28 h-28 mb-4">
                  <svg class="absolute inset-0 w-full h-full" viewBox="0 0 36 36">
                    <circle
                      class="text-gray-300"
                      cx="18"
                      cy="18"
                      r="15.9155"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                    ></circle>
                    <circle
                      class="text-blue-500"
                      cx="18"
                      cy="18"
                      r="15.9155"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linecap="round"
                      :stroke-dasharray="getStrokeDashArray(tech.level)"
                      stroke-dashoffset="25"
                      transform="rotate(-90 18 18)"
                    ></circle>
                  </svg>
                  <span
                    class="absolute inset-0 flex items-center justify-center text-blue-600 font-bold text-lg"
                  >
                    {{ tech.level }}%
                  </span>
                </div>
  
                <!-- Technology Name -->
                <span class="text-lg font-semibold text-gray-700">
                  {{ tech.name }}
                </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        categorizedTechnologies: [
          {
            title: "Programming Languages",
            technologies: [
              { name: "Java", level: 90 },
              { name: "Python", level: 85 },
              { name: "JavaScript", level: 80 },
              { name: "C++", level: 75 },
              { name: "Golang", level: 70 },
            ],
          },
          {
            title: "Web Technologies",
            technologies: [
              { name: "HTML", level: 95 },
              { name: "CSS", level: 90 },
            ],
          },
          {
            title: "Cloud Platforms",
            technologies: [
              { name: "AWS", level: 85 },
              { name: "Azure", level: 80 },
              { name: "Google Cloud", level: 75 },
            ],
          },
          {
            title: "Databases",
            technologies: [
              { name: "MySQL", level: 90 },
              { name: "SQLite", level: 80 },
            ],
          },
          {
            title: "Tools & Frameworks",
            technologies: [
              { name: "Docker", level: 85 },
              { name: "Kubernetes", level: 80 },
              { name: "React", level: 75 },
              { name: "Vue.js", level: 70 },
              { name: "PyCaret", level: 60 },
            ],
          },
        ],
      };
    },
    methods: {
      getStrokeDashArray(level) {
        const radius = 15.9155;
        const circumference = 2 * Math.PI * radius;
        const dashArray = (level / 100) * circumference;
        return `${dashArray}, ${circumference}`;
      },
    },
  };
  </script>
  
  <style>
  /* Progress Circle Animations */
  svg circle {
    transition: stroke-dasharray 0.6s ease;
  }
  
  /* Section Background */
  .bg-gradient-to-b {
    background: linear-gradient(to bottom, #ebf8ff, #bfdbfe);
  }
  
  /* Hover Effects */
  .shadow-lg:hover {
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
  }
  
  .transform:hover {
    transform: scale(1.05);
  }
  </style>
  