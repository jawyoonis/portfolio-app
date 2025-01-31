<template>
  <div>
    <!-- Add Navbar -->
    <Navbar />

    <!-- Main Components -->
    <HeroSection />
    <AboutMe />
    <Projects />
    <Contact />
    

  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import HeroSection from "./components/HeroSection.vue";
import AboutMe from "./components/AboutMe.vue";
import Projects from "./components/Projects.vue";
import Contact from "./components/Contact.vue";
import HeroSlice from "./components/slices/HeroSlice.vue";
import AboutSlice from "./components/slices/AboutSlice.vue";
import ProjectsSlice from "./components/slices/ProjectsSlice.vue";
import ContactSlice from "./components/slices/ContactSlice.vue";

export default {
  components: {
    Navbar,
    HeroSection, // From main component folder
    AboutMe, // From main component folder
    Projects, // From main component folder
    Contact, // From main component folder

    
  },
};
</script>
