<template>
  <stored-resources :stored-resources="storedResources"></stored-resources>
</template>

<script>
import StoredResources from "./components/LearningResources/StoredResources.vue";

export default {
    
  components: {
    StoredResources,
  },
  data() {
    return {
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
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");

* {
  box-sizing: border-box;
}

html {
  font-family: "Roboto", sans-serif;
}

body {
  margin: 0;
}
</style>
