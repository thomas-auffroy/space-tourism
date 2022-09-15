<script setup>
import HeaderComponent from "../components/HeaderComponent.vue";
</script>

<template>
  <div class="background">
    <HeaderComponent />
    <main>
      <div class="text">
        <h5>so, you want to travel to</h5>
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
  </div>
</template>

<style scoped>
.background {
  height: 100vh;
  width: 100vw;
  position: absolute;
  background: url("../assets/images/home/background-home-desktop.jpg")
    center/cover no-repeat;
}

main {
  display: flex;
  justify-content: space-around;

  margin-top: 250px;
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

.text p {
  word-spacing: 7px;
}

button {
  align-self: flex-end;
  height: 275px;
  width: 275px;

  border-radius: 50%;
  text-align: center;

  background-color: var(--color-white);
}
</style>
