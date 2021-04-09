<template>
  <button :class="mode">{{ type }}</button>
</template>

<script>
export default {
  props: ["type", "mode"],
};
</script>

<style scoped>
button {
  padding: 0.75rem 1.5rem;
  font-family: inherit;
  background-color: #4d9ab1;
  border: 1px solid #4d9ab1;
  color: white;
  cursor: pointer;
}

button:hover,
button:active {
  background-color: #266c81;
  border-color: #266c81;
}

.flat {
  background-color: transparent;
  color: #4d9ab1;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #266c81;
  color: #fff;
}
</style>
