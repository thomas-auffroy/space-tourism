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
  height: 100vh;
  width: 100vw;
  position: absolute;
  background: url("../assets/images/technology/background-technology-desktop.jpg")
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
