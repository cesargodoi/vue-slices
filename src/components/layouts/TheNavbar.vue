<template>
  <div>
    <nav>
      <span>{{ title }}</span>
      <div>
        <base-button @click="altTab('show-slices')">
          Show Slices
        </base-button>
        <base-button @click="altTab('add-slice')">
          Add Slice
        </base-button>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "TheNavbar",
  props: { title: String },
  methods: {
    altTab(tab) {
      this.$emit("alternateTab", tab);
    },
  },
  emits: ["alternateTab"],
};
</script>

<style scoped>
div {
  display: flex;
  justify-content: center;
  width: 100%;
  margin: 0;
  padding: 1%x;
  color: antiquewhite;
  background-color: #0d6b37;
}

nav {
  width: 90%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav span {
  padding: 1rem 0;
  font-size: 24pt;
  font-weight: bolder;
}

nav div {
  display: flex;
  justify-content: flex-end;
}
</style>
