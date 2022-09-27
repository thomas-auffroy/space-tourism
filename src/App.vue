<script setup>
import { RouterView } from "vue-router";

import { onMounted, onUnmounted, ref } from "vue";

const windowProperties = ref({
  height: window.innerHeight,
  width: window.innerWidth,
  format: getFormat(),
});

onMounted(() => {
  window.addEventListener("resize", onResize);
});
onUnmounted(() => {
  window.removeEventListener("resize", onResize);
});

function onResize() {
  windowProperties.value.height = window.innerHeight;
  windowProperties.value.width = window.innerWidth;
  windowProperties.value.format = getFormat();
}

function getFormat() {
  if (window.innerWidth > 1024) {
    return "desktop";
  } else if (window.innerWidth > 700) {
    return "tablet";
  } else {
    return "mobile";
  }
}
</script>

<template>
  <RouterView :windowFormat="windowProperties.format" />
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
