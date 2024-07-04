<script setup>
import Navbar from "./components/Navbar.vue";
import MainComp from "./components/MainComp.vue";
import { onMounted } from "vue";
import { useStore } from "./store/store";
import { storeToRefs } from "pinia";

const store = useStore();
const { weatherData, toggle } = storeToRefs(store);

onMounted(() => {
  // store.dispatch("getWeather");
  store.getWeather();
});
</script>

<template>
  <Navbar />
  <div v-if="!toggle">
    <MainComp />
  </div>
  <div v-else>
    <div class="about-text">
      <h2>About Weather App</h2>
      <h1>냉무</h1>
    </div>
  </div>
</template>

<style scoped lang="scss"></style>
