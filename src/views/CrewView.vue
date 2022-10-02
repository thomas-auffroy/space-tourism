<script setup>
import DisplayCrew from "../components/DisplayCrew.vue";

import { onMounted } from "vue";

const emits = defineEmits(["section"]);

onMounted(() => {
  emits("section", "crew");
});
</script>

<template>
  <h5><span>02</span> meet your crew</h5>
  <DisplayCrew />
</template>
