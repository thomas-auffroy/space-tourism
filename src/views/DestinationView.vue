<script setup>
import HeaderComponent from "../components/HeaderComponent.vue";
import DisplayDestination from "../components/DisplayDestination.vue";
</script>

<template>
  <div class="background">
    <HeaderComponent />
    <h5><span>01</span> pick your destination</h5>
    <DisplayDestination />
  </div>
</template>

<style scoped>
.background {
  height: 100vh;
  width: 100vw;
  position: absolute;
  background: url("../assets/images/destination/background-destination-desktop.jpg")
    center/cover no-repeat;
}
</style>
