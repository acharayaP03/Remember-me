<template>
  <div>
    <base-card>
      <base-button
        @click="setSelectedComponent('add-resources')"
        :mode="selectedComponenet === 'add-resources' ? null : 'flat'"
        >Add Resources</base-button
      >
      <base-button
        @click="setSelectedComponent('stored-resources')"
        :mode="selectedComponenet === 'stored-resources' ? null : 'flat'"
        >Stored Resources</base-button
      >
    </base-card>
    <component :is="selectedComponenet"></component>
  </div>
</template>

<script>
import StoredResources from "./StoredResources.vue";
import AddResources from "./AddResources.vue";
export default {
  components: {
    StoredResources,
    AddResources,
  },
  data() {
    return {
      selectedComponenet: "stored-resources",
      storedResources: [
        {
          id: "official-guide",
          title: "Offical Guide",
          description: "The official Vue.js documentation",
          link: "https://vuejs.org",
        },
        {
          id: "official-guide",
          title: "Official guide for React",
          description: "The official React.js documentation",
          link: "https://react.js",
        },
      ],
    };
  },
  provide() {
    return {
      resources: this.storedResources,
    };
  },
  methods: {
    setSelectedResources(element) {
      this.selectedComponenet = element;
    },
  },
};
</script>

<style lang="scss" scoped></style>
