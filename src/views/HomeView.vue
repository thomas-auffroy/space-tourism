<script setup>
import HeaderComponent from "../components/HeaderComponent.vue";

import bgDesktop from "@/assets/images/home/background-home-desktop.jpg";
import bgTablet from "@/assets/images/home/background-home-tablet.jpg";
import bgMobile from "@/assets/images/home/background-home-mobile.jpg";

import { onMounted, onUnmounted, onUpdated } from "vue";

const props = defineProps({
  windowFormat: {
    type: String,
    required: true,
    default: "",
  },
});

onMounted(() => {
  onPropsUpdate();
});

onUpdated(() => {
  onPropsUpdate();
});

onUnmounted(() => {
  document.body.style.backgroundImage = "";
});
function onPropsUpdate() {
  if (props.windowFormat === "desktop") {
    document.body.style.backgroundImage = `url(${bgDesktop})`;
  } else if (props.windowFormat === "tablet") {
    document.body.style.backgroundImage = `url(${bgTablet})`;
  } else if (props.windowFormat === "mobile") {
    document.body.style.backgroundImage = `url(${bgMobile})`;
  }
}
</script>

<template>
  <HeaderComponent />
  <main>
    <div class="text">
      <h5 class="no-css">so, you want to travel to</h5>
      <br />
      <h1>space</h1>
      <br />
      <p>
        Let’s face it; if you want to go to space, you might as well genuinely
        go to outer space and not hover kind of on the edge of it. Well sit
        back, and relax because we’ll give you a truly out of this world
        experience!
      </p>
    </div>
    <button>Explore</button>
  </main>
</template>

<style scoped>
main {
  display: flex;
  justify-content: space-around;

  margin-top: 10%;
}

.text {
  width: 450px;
}

.text :not(h1) {
  color: var(--color-blue-white);
}
.text h1 {
  color: var(--color-white);
}

button {
  align-self: flex-end;
  height: 275px;
  width: 275px;

  border-radius: 50%;
  text-align: center;

  background-color: var(--color-white);
  color: var(--color-black);
  cursor: pointer;
}
button:hover {
  box-shadow: 0 0 0 87px rgba(255, 255, 255, 0.1);
}

/* tablet */
@media only screen and (min-width: 760px) and (max-width: 1024px) {
  main {
    flex-direction: column;
    margin-top: 105px;
    gap: 156px;

    text-align: center;
  }
  .text,
  button {
    align-self: center;
  }
}
</style>
