<template>
    <div class="text-5xl hover:scale-125 transition-transform duration-300">
      <font-awesome-icon :icon="icon" />
    </div>
  </template>
  
  <script>
  import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
  import { faGithub, faLinkedin } from "@fortawesome/free-brands-svg-icons";
  
  export default {
    components: { FontAwesomeIcon },
    props: {
      icon: {
        type: Object,
        required: true, // Pass an icon like `faGithub` or `faLinkedin`
      },
    },
  };
  </script>
  