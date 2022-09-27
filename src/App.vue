<script setup>
import { RouterView } from "vue-router";
import HeaderComponent from "./components/HeaderComponent.vue";
import { onMounted, onUnmounted, ref } from "vue";

onMounted(() => {
  window.addEventListener("resize", onResize);
});
onUnmounted(() => {
  window.removeEventListener("resize", onResize);
});

function onResize() {
  imageURL.value = `url(src/assets/images/${activeSection.value}/background-${
    activeSection.value
  }-${getFormat()}.jpg)`;
}

function getFormat() {
  if (window.innerWidth > 1024) {
    return "desktop";
  } else if (window.innerWidth > 760) {
    return "tablet";
  } else {
    return "mobile";
  }
}

function onSectionChange(sectionName) {
  activeSection.value = sectionName;
  imageURL.value = `url(src/assets/images/${sectionName}/background-${sectionName}-${getFormat()}.jpg)`;
}

const imageURL = ref("");
const activeSection = ref("");
</script>

<template>
  <div id="full-width-background"></div>
  <HeaderComponent />
  <RouterView @section="onSectionChange" />
</template>

<style>
h5:not(.no-css) {
  color: var(--color-white);
  margin-top: 4%;
  margin-left: 165px;
}

h5:not(.no-css) span {
  font-weight: bold;
  opacity: 25%;
  margin-right: 10px;
}
/* tablet */
@media only screen and (min-width: 760px) and (max-width: 1024px) {
  h5:not(.no-css) {
    margin-left: 40px;
    margin-top: 40px;
  }
}
</style>

<style scoped>
#full-width-background {
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;

  width: 100%;
  min-height: 100vh;

  background-repeat: no-repeat;
  background-clip: border-box;
  background-size: cover;
  background-position: center;

  background-image: v-bind(imageURL);
}
</style>
