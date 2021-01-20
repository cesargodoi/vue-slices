<template>
  <base-card>
    <h2>{{ slice.slice }}</h2>
    <button>X</button>
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
