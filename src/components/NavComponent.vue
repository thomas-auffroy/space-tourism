<script setup>
import { RouterLink, useRoute } from "vue-router";

const path = useRoute().path;
</script>

<template>
  <nav>
    <ul>
      <li :class="path === '/' ? 'active' : ''">
        <span>00</span><RouterLink to="/">Home</RouterLink>
      </li>
      <li :class="path === '/destination' ? 'active' : ''">
        <span>01</span><RouterLink to="/destination">Destination</RouterLink>
      </li>
      <li :class="path === '/crew' ? 'active' : ''">
        <span>02</span><RouterLink to="/crew">Crew</RouterLink>
      </li>
      <li :class="path === '/technology' ? 'active' : ''">
        <span>03</span><RouterLink to="/technology">Technology</RouterLink>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
nav {
  width: 60%;
  height: 100%;
  color: var(--color-white);
  background-color: rgba(255, 255, 255, 0.04);
  backdrop-filter: blur(15px);
}

ul {
  display: flex;
  align-items: center;
  gap: 50px;
  height: 100%;
  margin-left: 20%;
}

ul li {
  display: flex;
  align-items: center;
  height: 100%;
  position: relative;
}
li:hover::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 3px;
  bottom: 0;
  left: 0;
  background-color: var(--color-white);
  z-index: -1;
  opacity: 50%;
}
li span {
  font-weight: bold;
  margin-right: 10px;

  position: absolute;
  z-index: -1;
}

li a {
  display: flex;
  align-items: center;
  height: 100%;
  width: 100%;

  padding-left: 30px;
}

.active::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 3px;
  bottom: 0;
  left: 0;
  background-color: var(--color-white);
  z-index: -1;
  opacity: 1 !important; /* Not to be overlapped by hover state */
}
</style>
