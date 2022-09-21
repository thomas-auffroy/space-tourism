<script setup>
import HeaderComponent from "../components/HeaderComponent.vue";
import DisplayCrew from "../components/DisplayCrew.vue";
</script>

<template>
  <div class="background">
    <HeaderComponent />
    <h5><span>02</span> meet your crew</h5>
    <DisplayCrew />
  </div>
</template>

<style scoped>
.background {
  background-image: url("../assets/images/crew/background-crew-desktop.jpg");
}
</style>
