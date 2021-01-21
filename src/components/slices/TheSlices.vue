<template>
  <div>
    <base-card>
      <base-button :bClass="showBClass" @click="alternateTab('show-slices')">
        Show Slices
      </base-button>
      <base-button :bClass="addBClass" @click="alternateTab('add-slice')">
        Add Slice
      </base-button>
    </base-card>
    <keep-alive>
      <component :is="selectedTab" />
    </keep-alive>
  </div>
</template>

<script>
import AddSlice from "./AddSlice.vue";
import ShowSlices from "./ShowSlices.vue";
export default {
  components: { ShowSlices, AddSlice },
  name: "TheSlices",
  data() {
    return {
      selectedTab: "show-slices",
      storedSlices: [
        {
          id: 1,
          slice: "$emit",
          description:
            "Mussum Ipsum, cacilds vidis litro abertis. Casamentiss faiz malandris se pirulitá.",
          link: "https://vuejs.org/",
        },
        {
          id: 2,
          slice: "v-for",
          description:
            "Manduma pindureta quium dia nois paga. In elementis mé pra quem é amistosis quis leo.",
          link: "https://stackoverflow.com/",
        },
      ],
    };
  },
  computed: {
    showBClass() {
      return this.selectedTab === "show-slices" ? null : "flat";
    },
    addBClass() {
      return this.selectedTab === "add-slice" ? null : "flat";
    },
  },
  methods: {
    alternateTab(tab) {
      return (this.selectedTab = tab);
    },
    setSlice(slice, descr, link) {
      const newSlice = {
        id: new Date().toISOString(),
        slice: slice,
        description: descr,
        link: link,
      };
      this.storedSlices.unshift(newSlice);
    },
  },
  provide() {
    return {
      slices: this.storedSlices,
      setSlice: this.setSlice,
    };
  },
};
</script>

<style scoped>
div {
  margin: auto;
  width: 80%;
}
</style>
