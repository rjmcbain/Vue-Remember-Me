<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<script>
export default {
  data() {
    return {
      title: "Resources",
    };
  },
};
</script>

<style scoped>
header {
  width: 100%;
  height: 5rem;
  background-color: #4d9ab1;
  display: flex;
  justify-content: center;
  align-items: center;
}
header h1 {
  color: white;
  margin: 0;
}
</style>
