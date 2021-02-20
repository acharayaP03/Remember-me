<template>
  <base-card>
    <form @submit.prevent="submitResources">
      <div class="form-control">
        <label for="title">Title</label>
        <input type="text" id="title" name="title" ref="title" />
      </div>
      <div class="form-control">
        <label for="description">
          Description
        </label>
        <textarea
          cols="10"
          rows="10"
          id="description"
          name="description"
          ref="description"
        ></textarea>
      </div>
      <div class="form-control">
        <label for="url">Url</label>
        <input type="url" id="url" name="url" ref="url" />
      </div>
      <div>
        <base-button type="submit">Add Resources</base-button>
      </div>
    </form>
  </base-card>
</template>
<script>
export default {
  inject: ["addResources"],
  methods: {
    submitResources() {
      const newTitle = this.$refs.title.value;
      const newDescription = this.$refs.description.value;
      const newUrl = this.$refs.url.value;

      this.addResources(newTitle, newDescription, newUrl);
    },
  },
};
</script>
<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>
