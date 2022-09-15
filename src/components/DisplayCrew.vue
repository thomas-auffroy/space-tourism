<script setup>
import { ref, watchEffect } from "vue";
import * as property from "../assets/data.json";
const crews = property.crew;

const crewPicked = ref(null);
const index = ref();
localStorage.index ? (index.value = localStorage.indexCrew) : (index.value = 0); // Initialise la valeur du local storage

initCrew();

/**
 * A chaque modification de la valeur de l'index, on modifie le local storage
 */
watchEffect(function () {
  localStorage.setItem("indexCrew", index.value);
});

/**
 * Fonction trigger au clique d'un item de la liste <ul>
 * @param {Object} arg
 */
function chooseCrew(arg) {
  index.value = arg.target.attributes["data-index"].value;
  crewPicked.value = crews[index.value];
}

/**
 * Initialise la valeur du premier item choisi
 */
function initCrew() {
  if (localStorage.index) {
    crewPicked.value = crews[localStorage.index];
  } else {
    crewPicked.value = crews[0];
  }
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
      <h4 class="role">{{ crewPicked.role }}</h4>
      <h3 class="name">{{ crewPicked.name }}</h3>
      <p>{{ crewPicked.bio }}</p>
      <ul>
        <li
          v-for="(crew, index) in crews"
          :key="crew.index"
          :class="crewPicked.name == crew.name ? 'active' : ''"
          :data-index="index"
          @click="chooseCrew"
        ></li>
      </ul>
    </div>
    <picture>
      <source :srcset="getImageUrl(crewPicked.images.webp)" type="image/webp" />
      <img :src="getImageUrl(crewPicked.images.webp)" alt="" />
    </picture>
  </main>
</template>

<style scoped>
main {
  display: flex;
}

li {
  height: 15px;
  width: 15px;
  border-radius: 50%;
  background-color: var(--color-white);
  opacity: 17%;
}

li.active {
  opacity: 1;
}

.content {
  margin-top: 155px;
}
.name {
  margin-top: 15px;
  margin-bottom: 25px;
}

.content p {
  margin-bottom: 120px;
}

picture {
  height: fit-content;
}
</style>
