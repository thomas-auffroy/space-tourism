<script setup>
import HeaderComponent from "../components/HeaderComponent.vue";
import DisplayTechnology from "../components/DisplayTechnology.vue";
</script>

<template>
  <div class="background">
    <HeaderComponent />
    <h5><span>03</span> space launch 101</h5>
    <DisplayTechnology />
  </div>
</template>

<style scoped>
.background {
  background-image: url("../assets/images/technology/background-technology-desktop.jpg");
}
</style>
