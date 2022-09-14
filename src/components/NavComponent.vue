<script setup>
import { RouterLink, useRoute } from "vue-router";

const route = useRoute();
console.log(route);
</script>

<template>
  <nav>
    <ul>
      <li class="active">
        <span>00</span><RouterLink to="/">Home</RouterLink>
      </li>
      <li>
        <span>01</span><RouterLink to="/destination">Destination</RouterLink>
      </li>
      <li><span>02</span><RouterLink to="/crew">Crew</RouterLink></li>
      <li>
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
  margin-left: 15%;
}

ul li {
  display: flex;
  align-items: center;
  height: 100%;
  position: relative;
}
li span {
  font-weight: bold;
  margin-right: 10px;
}

.active ::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 3px;
  bottom: 0;
  left: 0;
  background-color: white;
}
</style>
