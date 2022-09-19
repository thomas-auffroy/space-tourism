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
  background-image: url("../assets/images/destination/background-destination-desktop.jpg");
}

/* tablet */
@media only screen and (min-width: 760px) and (max-width: 1024px) {
  .background {
    background-image: url("../assets/images/destination/background-destination-tablet.jpg");
  }
}
</style>
