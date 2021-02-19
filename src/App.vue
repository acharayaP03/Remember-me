
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
  <!-- Compiler warning  -->
</template>

<script>
import LearningResources from './components/LearningResources/LearningResources.vue';
export default {
  components: {
    LearningResources
  },
  data() {
    return {
      storedResources: [
        {
          id: 'official-guide',
          title: 'Offical Guide',
          description: 'The official Vue.js documentation',
          link: 'https://vuejs.org'
        },
        {
          id: 'official-guide',
          title: 'Official guide for React',
          description: 'The official React.js documentation',
          link: 'https://react.js'
        }
      ]
    };
  }
};
</script>