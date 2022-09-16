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

  position: relative;
}

header::before {
  content: "";
  position: absolute;
  width: calc(45% - 160px);
  height: 1px;

  top: calc((100% - 4px) / 2);
  left: calc(165px - 55px);

  background-color: var(--color-white);
  opacity: 25%;
  z-index: 1;
}
.icon {
  margin: auto 0;
}

/* tablet */
@media only screen and (min-width: 700px) and (max-width: 1024px) {
  header::before {
    content: none;
  }

  header {
    margin-top: 0;
    margin-left: 40px;
  }
}
</style>
