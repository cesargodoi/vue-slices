<template>
  <the-navbar
    title="Slices"
    :selectedTab="selectedTab"
    @alternateTab="alternateTab"
  />
  <the-slices :selectedTab="selectedTab" @showSlices="showSlices" />
</template>

<script>
import TheNavbar from "./components/layouts/TheNavbar.vue";
import TheSlices from "./components/slices/TheSlices.vue";

export default {
  name: "App",
  components: { TheSlices, TheNavbar },
  data() {
    return {
      selectedTab: "show-slices",
    };
  },
  methods: {
    alternateTab(tab) {
      return (this.selectedTab = tab);
    },
    showSlices() {
      this.selectedTab = "show-slices";
    },
  },
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
