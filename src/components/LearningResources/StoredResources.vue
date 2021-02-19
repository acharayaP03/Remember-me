<template>
  <ul>
    <learning-resources
      v-for="resources in storedResources"
      :key="resources.id"
      :title="resources.title"
      :description="resources.description"
      :link="resources.link"
    ></learning-resources>
  </ul>
</template>

<script>
import LearningResources from "./LearningResources.vue";
export default {
  components: {
    LearningResources,
  },
  props: {
    storedResources: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}</style>
