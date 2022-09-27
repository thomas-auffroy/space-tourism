<script setup>
import DisplayDestination from "../components/DisplayDestination.vue";

import { onMounted } from "vue";

const emits = defineEmits(["section"]);

onMounted(() => {
  emits("section", "destination");
});
</script>

<template>
  <h5><span>01</span> pick your destination</h5>
  <DisplayDestination />
</template>

<style scoped>
/* tablet */
@media only screen and (min-width: 760px) and (max-width: 1024px) {
}
</style>
