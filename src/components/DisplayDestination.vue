<script setup>
import { ref } from "vue";
import * as property from "../assets/data.json";
const destinations = property.destinations;
console.log(destinations);

const destinationPicked = ref(null);
destinationPicked.value = destinations[0];
</script>

<template>
  <main>
    <img src="../assets/images/destination/image-europa.png" alt="" />
    <div class="content">
      <ul>
        <li
          v-for="destination in destinations"
          :key="destination.name"
          :class="destinationPicked.name == destination.name ? 'active' : ''"
        >
          {{ destination.name }}
        </li>
      </ul>
      <h2>MOON</h2>
      <p class="description">
        See our planet as you’ve never seen it before. A perfect relaxing trip
        away to help regain perspective and come back refreshed. While you’re
        there, take in some history by visiting the Luna 2 and Apollo 11 landing
        sites.
      </p>
      <hr />
      <div class="info">
        <div>
          <p class="subheading-2">avg. distance</p>
          <p class="subheading-1">384.000 km</p>
        </div>

        <div>
          <p class="subheading-2">est. travel time</p>
          <p class="subheading-1">3 days</p>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.active::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 3px;
  bottom: -12px;
  left: 0;
  background-color: var(--color-white);
}
.active {
  color: var(--color-white);
}

main {
  display: flex;
  justify-content: center;
  gap: 160px;
  margin-top: 175px;
}
img {
  height: fit-content;
  align-self: flex-end;
}
.content {
  width: 445px;
}
h2 {
  color: var(--color-white);
}
ul {
  display: flex;
  gap: 35px;

  margin-bottom: 37px;
}
li {
  font-family: "Barlow Condensed", sans-serif;
  font-size: 16px;
  letter-spacing: 2.7px;
  text-transform: uppercase;
  color: var(--color-blue-white);
  position: relative;
  margin-bottom: 12px;
}
.description {
  color: var(--color-blue-white);
}
hr {
  width: 100%;
  height: 1px;
  margin-top: 54px;
  margin-bottom: 28px;
  background-color: rgb(56, 59, 75);
}
.info {
  display: flex;
  justify-content: space-between;
}

.subheading-2 {
  color: var(--color-blue-white);
  margin-bottom: 10px;
}
.subheading-1 {
  color: var(--color-white);
}
</style>
