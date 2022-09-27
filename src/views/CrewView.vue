<script setup>
import DisplayCrew from "../components/DisplayCrew.vue";

import bgDesktop from "@/assets/images/crew/background-crew-desktop.jpg";
import bgTablet from "@/assets/images/crew/background-crew-tablet.jpg";
import bgMobile from "@/assets/images/crew/background-crew-mobile.jpg";

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
  <h5><span>02</span> meet your crew</h5>
  <DisplayCrew />
</template>

<style scoped></style>
