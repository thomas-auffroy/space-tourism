<script setup>
import DisplayTechnology from "../components/DisplayTechnology.vue";

import { onMounted } from "vue";

const emits = defineEmits(["section"]);

onMounted(() => {
  emits("section", "technology");
});
</script>

<template>
  <h5><span>03</span> space launch 101</h5>
  <DisplayTechnology />
</template>
