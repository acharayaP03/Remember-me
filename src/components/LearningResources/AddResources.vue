<template>
  <base-dialog v-if="isInvalid" title="Invalid Input" @close="confirmError">
    <template #default>
      <p class="error">At least one input value is invalid.</p>
      <p>Please check all inputs and make sure you eneter at leaset one value.</p>
    </template>
    <template v-slot:actions>
      <base-button @click="confirmError">Okay</base-button>
    </template>
  </base-dialog>
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
  data() {
    return {
      isInvalid: false,
    };
  },
  methods: {
    submitResources() {
      const newTitle = this.$refs.title.value;
      const newDescription = this.$refs.description.value;
      const newUrl = this.$refs.url.value;
      //check if the the fields are empty
      if (newTitle.trim() === "" || newDescription.trim() === "" || newUrl.trim() === "") {
        this.isInvalid = true;

        return;
      }

      this.addResources(newTitle, newDescription, newUrl);
    },
    confirmError() {
      this.isInvalid = false;
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
