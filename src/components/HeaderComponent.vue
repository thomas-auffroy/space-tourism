<script setup>
import NavComponent from "./NavComponent.vue";
</script>

<template>
  <header>
    <div class="icon">
      <img src="../assets/images/shared/logo.svg" alt="Logo de Space Tourism" />
    </div>
    <NavComponent />
  </header>
</template>

<style scoped>
header {
  height: 100px;
  display: flex;
  justify-content: space-between;

  margin-top: 45px;
  margin-left: 55px;
}

.icon {
  margin: auto 0;
}
</style>
