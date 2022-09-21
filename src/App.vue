<script setup>
import { RouterView } from "vue-router";
</script>

<template>
  <RouterView />
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
