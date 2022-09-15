<script setup>
import { ref } from "vue";
import * as property from "../assets/data.json";
const destinations = property.destinations;
console.log(destinations);

const destinationPicked = ref(null);
destinationPicked.value = destinations[0];

console.log(getImageUrl());

function chooseDestination(arg) {
  const value = arg.target.attributes["data-index"].value;
  destinationPicked.value = destinations[value];
}

function getImageUrl(path) {
  return new URL(path, import.meta.url).href;
}
</script>

<template>
  <main>
    <picture>
      <source
        :srcset="getImageUrl(destinationPicked.images.webp)"
        type="image/webp"
      />
      <img :src="getImageUrl(destinationPicked.images.webp)" alt="" />
    </picture>
    <div class="content">
      <ul>
        <li
          v-for="(destination, index) in destinations"
          :key="destination.index"
          :class="destinationPicked.name == destination.name ? 'active' : ''"
          :data-index="index"
          @click="chooseDestination"
        >
          {{ destination.name }}
        </li>
      </ul>
      <h2>{{ destinationPicked.name }}</h2>
      <p class="description">
        {{ destinationPicked.description }}
      </p>
      <hr />
      <div class="info">
        <div>
          <p class="subheading-2">avg. distance</p>
          <p class="subheading-1">{{ destinationPicked.distance }}</p>
        </div>

        <div class="travel">
          <p class="subheading-2">est. travel time</p>
          <p class="subheading-1">{{ destinationPicked.travel }}</p>
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
picture {
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
  cursor: pointer;
}
.description {
  min-height: 128px;
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
  position: relative;
}
.travel {
  position: absolute;
  left: 220px;
  top: 0;
}

.subheading-2 {
  color: var(--color-blue-white);
  margin-bottom: 10px;
}
.subheading-1 {
  color: var(--color-white);
}
</style>
