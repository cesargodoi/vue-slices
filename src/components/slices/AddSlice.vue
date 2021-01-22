<template>
  <base-dialog v-if="showErrors" @close="confirmError">
    <template #header>
      <h2>Something went wrong</h2>
    </template>
    <template #default>
      <p>Unfurtenately, at least one input value is invalid.</p>
      <p>
        Please check all inputs and make sure you enter at least a few caracters
        into each input field.
      </p>
    </template>
    <template #actions>
      <base-button class="error" @click="confirmError">Okay</base-button>
    </template>
  </base-dialog>
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
      <div class="form-control">
        <base-button type="submit">Add Resource</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  name: "AddSlice",
  inject: ["setSlice"],
  data() {
    return {
      showErrors: false,
    };
  },
  methods: {
    getSlice() {
      const slice = this.$refs.slice.value;
      const description = this.$refs.description.value;
      const link = this.$refs.link.value;

      if (!slice.trim() || !description.trim() || !link.trim()) {
        this.showErrors = true;
        return;
      }
      this.setSlice(slice, description, link);
    },
    confirmError() {
      this.showErrors = false;
    },
  },
};
</script>

<style scoped>
.form-control {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  margin: auto;
  display: block;
  width: 97%;
  font: inherit;
  padding: 10px;
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
