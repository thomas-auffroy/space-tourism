<script setup>
import HeaderComponent from "../components/HeaderComponent.vue";
import DisplayTechnology from "../components/DisplayTechnology.vue";

import bgDesktop from "@/assets/images/technology/background-technology-desktop.jpg";
import bgTablet from "@/assets/images/technology/background-technology-tablet.jpg";
import bgMobile from "@/assets/images/technology/background-technology-mobile.jpg";

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
  <h5><span>03</span> space launch 101</h5>
  <DisplayTechnology />
</template>

<style scoped></style>
