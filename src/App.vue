<template>
  <the-header />
</template>

<script>
import TheHeader from "./components/layouts/TheHeader";
export default {
  name: "App",
  components: { TheHeader },
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
