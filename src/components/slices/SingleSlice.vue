<template>
  <base-card>
    <header>
      <h2>{{ slice.slice }}</h2>
      <base-button bClass="flat">delete</base-button>
    </header>
    <p>{{ slice.description }}</p>
    <a :href="slice.link">Saiba mais</a>
  </base-card>
</template>

<script>
export default {
  name: "TheSlices",
  props: { slice: Object },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: stretch;
}
</style>
