<template>
  <div>
    <base-card>
      <base-button @click="setSelectedComponent('add-resources')">Add Resources</base-button>
      <base-button @click="setSelectedComponent('stored-resources')">Stored Resources</base-button>
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
