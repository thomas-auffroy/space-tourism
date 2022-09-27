<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <nav>
    <ul>
      <li tabindex="0" @keyup.enter="$router.push({ name: 'home' })">
        <span>00</span><RouterLink to="/" tabindex="-1">Home</RouterLink>
      </li>
      <li tabindex="0" @keyup.enter="$router.push({ name: 'destination' })">
        <span>01</span
        ><RouterLink to="/destination" tabindex="-1">Destination</RouterLink>
      </li>
      <li tabindex="0" @keyup.enter="$router.push({ name: 'crew' })">
        <span>02</span><RouterLink to="/crew" tabindex="-1">Crew</RouterLink>
      </li>
      <li tabindex="0" @keyup.enter="$router.push({ name: 'technology' })">
        <span>03</span
        ><RouterLink to="/technology" tabindex="-1">Technology</RouterLink>
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
li:hover::after,
li:focus::after {
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

.router-link-exact-active::after {
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

@media only screen and (max-width: 1230px) {
  ul {
    margin-left: 100px;
    gap: 5%;
  }
}

/* tablet */
@media only screen and (min-width: 760px) and (max-width: 1024px) {
  ul {
    margin-left: 50px;
    gap: 37px;
  }
  li span {
    display: none;
  }
  li {
    font-family: "Barlow Condensed", sans-serif;
    color: var(--color-white);
    font-size: 14px;
    letter-spacing: 2.35px;
  }
  li a {
    padding-left: 0;
  }
}
</style>
