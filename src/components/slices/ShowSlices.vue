<template>
  <single-slice v-for="slice in slices" :key="slice.id" :slice="slice" />
</template>

<script>
import SingleSlice from "./SingleSlice.vue";
export default {
  components: { SingleSlice },
  name: "ShowSlices",
  inject: ["slices"],
};
</script>
