<template>
  <base-card>
    <header>
      <h2>{{ slice.slice }}</h2>
      <base-button bClass="flat" @click="delSlice(slice.id)">
        delete
      </base-button>
    </header>
    <p>{{ slice.description }}</p>
    <a :href="slice.link">Saiba mais</a>
  </base-card>
</template>

<script>
export default {
  name: "SilgleSlice",
  inject: ["delSlice"],
  props: { slice: Object },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
