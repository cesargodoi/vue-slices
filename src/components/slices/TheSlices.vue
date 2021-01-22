<template>
  <div>
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
  props: { selectedTab: String },
  data() {
    return {
      storedSlices: [
        {
          id: 1,
          slice: "v-if",
          description:
            "A diretiva v-if é usada para renderizar condicionalmente um bloco. O bloco só será renderizado se a expressão da diretiva retornar um valor verdadeiro.",
          link: "https://br.vuejs.org/v2/guide/conditional.html",
        },
        {
          id: 2,
          slice: "v-for",
          description:
            "A diretiva v-for é usada para renderizar uma lista de elementos com base nos dados de um Array. Sua sintaxe é: 'item in items'. Onde items é a fonte de dados e item é um apelido para o elemento iterado.",
          link: "https://br.vuejs.org/v2/guide/list.html",
        },
      ],
    };
  },
  methods: {
    setSlice(slice, descr, link) {
      const newSlice = {
        id: new Date().toISOString(),
        slice: slice,
        description: descr,
        link: link,
      };
      this.storedSlices.unshift(newSlice);
      this.$emit("showSlices");
    },
    delSlice(id) {
      let objIndex = this.storedSlices.findIndex((obj) => obj.id === id);
      this.storedSlices.splice(objIndex, 1);
    },
  },
  provide() {
    return {
      slices: this.storedSlices,
      setSlice: this.setSlice,
      delSlice: this.delSlice,
    };
  },
  emits: ["showSlices"],
};
</script>

<style scoped>
div {
  margin: auto;
  width: 90%;
}
</style>
