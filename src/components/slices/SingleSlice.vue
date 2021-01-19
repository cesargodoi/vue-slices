<template>
  <h2>{{ slice.slice }}</h2>
  <p>{{ slice.description }}</p>
  <ul>
    <li v-for="example in slice.examples" :key="example">{{ example }}</li>
  </ul>
</template>

<script>
export default {
  name: "TheSlices",
  props: { slice: Object },
};
</script>
