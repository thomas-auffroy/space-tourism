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
  height: 100vh;
  width: 100vw;
  position: absolute;
  background: url("../assets/images/destination/background-destination-desktop.jpg")
    center/cover no-repeat;
}

h5 {
  color: var(--color-white);
  margin-top: 75px;
  margin-left: 165px;
}

h5 span {
  font-weight: bold;
  opacity: 25%;
  margin-right: 10px;
}
</style>
