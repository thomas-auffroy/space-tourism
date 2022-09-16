<script setup>
import { ref, watchEffect } from "vue";
import * as property from "../assets/data.json";
const technologies = property.technology;

const technologyPicked = ref();
const index = ref();

localStorage.indexTechnology
  ? (index.value = localStorage.indexTechnology)
  : (index.value = 0); // Initialise la valeur du local storage

initDestination();

/**
 * A chaque modification de la valeur de l'index, on modifie le local storage
 */
watchEffect(function () {
  localStorage.setItem("indexTechnology", index.value);
});

/**
 * Initialise la valeur du premier item choisi
 */
function initDestination() {
  if (localStorage.indexTechnology) {
    technologyPicked.value = technologies[localStorage.indexTechnology];
  } else {
    technologyPicked.value = technologies[0];
  }
}

/**
 * Fonction trigger au clique d'un item de la liste <ul>
 * @param {Object} arg
 */
function chooseTechnology(arg) {
  index.value = arg.target.attributes["data-index"].value;
  technologyPicked.value = technologies[index.value];
}

/**
 * Permet d'encoder l'URL des images
 * @param {String} path
 */
function getImageUrl(path) {
  return new URL(path, import.meta.url).href;
}
</script>

<template>
  <main>
    <div class="content">
      <ul>
        <li
          v-for="(technology, index) in technologies"
          :key="index"
          @click="chooseTechnology"
          :data-index="index"
          :class="technology.name === technologyPicked.name ? 'active' : ''"
        >
          <h4>{{ index + 1 }}</h4>
        </li>
      </ul>
      <div class="info">
        <p class="like-nav">THE TERMINOLOGY…</p>

        <h3>{{ technologyPicked.name }}</h3>

        <p class="description">{{ technologyPicked.description }}</p>
      </div>
    </div>
    <img :src="getImageUrl(technologyPicked.images.portrait)" alt="" />
  </main>
</template>

<style scoped>
main {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-left: 165px;
}
.content {
  display: flex;
  gap: 80px;
}
.like-nav {
  color: var(--color-blue-white);
}
ul {
  display: flex;
  flex-direction: column;
  gap: 32px;
}
li {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 80px;
  width: 80px;
  border-radius: 50%;
  border: 1px solid rgba(255, 255, 255, 0.25);
  cursor: pointer;
}
li:hover {
  border: 1px solid rgba(255, 255, 255, 1);
}

h3 {
  margin-top: 11px;
  margin-bottom: 17px;
}
h4 {
  pointer-events: none;
}
li.active h4 {
  color: var(--color-black);
}

li.active {
  background-color: var(--color-white);
}

.description {
  max-width: 445px;
  height: 200px;
  color: var(--color-blue-white);
}
</style>
