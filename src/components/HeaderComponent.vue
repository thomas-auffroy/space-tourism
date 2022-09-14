<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <div class="icon">
    <img src="../assets/images/shared/logo.svg" alt="Logo de Space Tourism" />
  </div>
  <nav>
    <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/destination">Destination</RouterLink>
    <RouterLink to="/crew">Crew</RouterLink>
    <RouterLink to="/technology">Technology</RouterLink>
  </nav>
</template>

<style scoped>
nav {
  color: var(--color-white);
}
</style>
