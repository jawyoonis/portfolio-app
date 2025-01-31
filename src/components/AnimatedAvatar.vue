<template>
    <div ref="lottieContainer" class="w-48 h-48 mx-auto"></div>
  </template>
  
  <script>
  import lottie from "lottie-web";
  
  export default {
    props: {
      animationPath: {
        type: String,
        required: true, // URL or path to the Lottie animation JSON file
      },
    },
    mounted() {
      lottie.loadAnimation({
        container: this.$refs.lottieContainer,
        renderer: "svg",
        loop: true,
        autoplay: true,
        path: this.animationPath,
      });
    },
  };
  </script>
  
  <style>
  /* Optionally style the avatar container */
  </style>
  