<template>
  <h1>The Slices</h1>
  <ul>
    <single-slice v-for="slice in slices" :key="slice.id" :slice="slice" />
  </ul>
</template>

<script>
import SingleSlice from "./SingleSlice.vue";
export default {
  components: { SingleSlice },
  name: "TheSlices",
  data() {
    return {
      slices: [
        {
          id: 1,
          slice: "$emit",
          description:
            "Mussum Ipsum, cacilds vidis litro abertis. Casamentiss faiz malandris se pirulitá.",
          examples: ["https://vuejs.org/", "https://stackoverflow.com/"],
        },
        {
          id: 2,
          slice: "v-for",
          description:
            "Manduma pindureta quium dia nois paga. In elementis mé pra quem é amistosis quis leo.",
          examples: [
            "https://vuejs.org/",
            "https://stackoverflow.com/",
            "https://google.com",
          ],
        },
      ],
    };
  },
};
</script>
