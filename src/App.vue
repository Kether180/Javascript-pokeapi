<template>
  <div id="app">
    <header></header>

    <main>
      <img alt="Vue logo" class="logo" src="@/assets/pokemon-logo.png" />
      <Pokemon />
    </main>
  </div>
</template>

<script>
import Pokemon from "./components/Pokemon.vue";

export default {
  components: {
    Pokemon,
  },
};
</script>

<style>
#app {
  margin: 0 auto;
  width: auto;
  font-weight: normal;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  min-height: 100vh;
  text-align: center;
  color: #090e14;
  background: rgb(10, 10, 10);
  color: rgb(241, 233, 233);
  padding: 20px;
  min-width: 1024px;
  display: flex;
  align-items: center;
  background-size: 300px 100px;
  height: auto;
}

header {
  line-height: 1.5;
  display: flex;
  place-items: center;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
  align-items: center;
  width: 50%;
  height: 50%;
}

main {
  min-height: 100vh;
  max-width: 1280px;
  transition: color 0.5s, background-color 0.5s;
  line-height: 1.6;
  font-size: 15px;
}
</style>
