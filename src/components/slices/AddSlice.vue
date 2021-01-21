<template>
  <base-card>
    <form @submit.prevent="getSlice">
      <div class="form-control">
        <label for="slice">Slice</label>
        <input name="slice" id="slice" type="text" ref="slice" />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea
          name="description"
          id="description"
          rows="4"
          ref="description"
        ></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input name="link" id="link" type="url" ref="link" />
      </div>
      <div>
        <base-button type="submit">Add Resource</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  name: "AddSlice",
  inject: ["setSlice"],
  methods: {
    getSlice() {
      const slice = this.$refs.slice.value;
      const description = this.$refs.description.value;
      const link = this.$refs.link.value;
      this.setSlice(slice, description, link);
    },
  },
};
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #0d6d3880;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #0d6d3880;
  background-color: #e4faed;
}

.form-control {
  margin: 1rem 0;
}
</style>
