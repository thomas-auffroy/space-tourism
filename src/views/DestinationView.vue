<script setup>
import HeaderComponent from "../components/HeaderComponent.vue";
import DisplayDestination from "../components/DisplayDestination.vue";

import bgDesktop from "@/assets/images/destination/background-destination-desktop.jpg";
import bgTablet from "@/assets/images/destination/background-destination-tablet.jpg";
import bgMobile from "@/assets/images/destination/background-destination-mobile.jpg";

import { onMounted, onUnmounted, onUpdated } from "vue";

const props = defineProps({
  windowFormat: {
    type: String,
    required: true,
    default: "",
  },
});

onMounted(() => {
  onPropsUpdate();
});

onUpdated(() => {
  onPropsUpdate();
});

onUnmounted(() => {
  document.body.style.backgroundImage = "";
});
function onPropsUpdate() {
  if (props.windowFormat === "desktop") {
    document.body.style.backgroundImage = `url(${bgDesktop})`;
  } else if (props.windowFormat === "tablet") {
    document.body.style.backgroundImage = `url(${bgTablet})`;
  } else if (props.windowFormat === "mobile") {
    document.body.style.backgroundImage = `url(${bgMobile})`;
  }
}
</script>

<template>
  <HeaderComponent />
  <h5><span>01</span> pick your destination</h5>
  <DisplayDestination />
</template>

<style scoped>
/* tablet */
@media only screen and (min-width: 760px) and (max-width: 1024px) {
}
</style>
