<template>
  <div ref="lottieContainer" class="w-48 h-48 mx-auto"></div>
</template>

<script>
import lottie from "lottie-web";

export default {
  mounted() {
    lottie.loadAnimation({
      container: this.$refs.lottieContainer, // Bind Lottie animation to this container
      renderer: "svg",
      loop: true,
      autoplay: true,
      path: "https://assets9.lottiefiles.com/packages/lf20_5rqxpsox.json", // Replace with a Lottie animation URL
    });
  },
};
</script>

<style>
/* Optional custom styles for Avatar container */
</style>
