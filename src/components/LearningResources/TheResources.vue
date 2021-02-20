<template>
  <div>
    <base-card>
      <base-button @click="setSelectedComponent('stored-resources')" :mode="storedResourcesMode"
        >Stored Resources</base-button
      >
      <base-button @click="setSelectedComponent('add-resources')" :mode="addResourcesMode"
        >Add Resources</base-button
      >
    </base-card>
    <keep-alive>
      <component :is="selectedComponenet"></component>
    </keep-alive>
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
  computed: {
    storedResourcesMode() {
      return this.selectedComponenet === "stored-resources" ? null : "flat";
    },
    addResourcesMode() {
      return this.selectedComponenet === "add-resources" ? null : "flat";
    },
  },
  provide() {
    return {
      resources: this.storedResources,
      addResources: this.addResources,
    };
  },
  methods: {
    setSelectedComponent(element) {
      this.selectedComponenet = element;
    },
    addResources(title, description, link) {
      const newResources = {
        id: new Date().toISOString(),
        title,
        description,
        link,
      };
      this.storedResources.unshift(newResources);
      this.selectedComponenet = "stored-resources";
    },
  },
};
</script>

<style lang="scss" scoped></style>
