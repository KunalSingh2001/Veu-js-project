<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <ChildComponent name="John" />

  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <h1>Count: {{ store.count }}</h1>
  <button @click="store.increment">Increase</button>
  <router-view />
</template>

<script>
import ChildComponent from "./components/ChildComponent.vue";
import { useMainStore } from "./store/store";
export default {
  components: { ChildComponent },
  setup() {
    const store = useMainStore();
    return { store };
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
