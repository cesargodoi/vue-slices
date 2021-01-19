<template>
  <the-header />
  <the-slices />
</template>

<script>
import TheHeader from "./components/layouts/TheHeader.vue";
import TheSlices from "./components/slices/TheSlices.vue";

export default {
  name: "App",
  components: { TheHeader, TheSlices },
};
</script>

<style>
html,
body {
  margin: auto;
  width: 100%;
  height: 100%;
  font-family: sans-serif;
}
</style>
