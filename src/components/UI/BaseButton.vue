<template>
  <button :class="bClass">
    <slot />
  </button>
</template>

<script>
export default {
  props: {
    bClass: String,
  },
};
</script>

<style scoped>
button {
  padding: 0.75rem 1.5rem;
  font-family: inherit;
  border: 0;
  border-radius: 6px;
  color: white;
  background-color: #0d6d38;
  cursor: pointer;
}

button:hover,
button:active {
  background-color: #2c8554;
}

.flat {
  border: none;
  color: #0d6d38;
  background-color: transparent;
}

.flat:hover,
.flat:active {
  background-color: #cad4cf;
}
</style>
