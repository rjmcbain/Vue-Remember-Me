<template>
  <ul>
    <LearningResource
      v-for="res in resources"
      :key="res.id"
      :id="res.id"
      :title="res.title"
      :description="res.description"
      :link="res.link"
    />
  </ul>
</template>

<script>
import LearningResource from "../components/LearningResource";
export default {
  components: {
    LearningResource,
  },
  inject: ["resources"],
};
</script>

<style scoped>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
