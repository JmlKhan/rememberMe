<template>
  <div>
    <base-dialog
      v-if="isInvalidValue"
      title="Invalid Input"
      @close="confirmError"
    >
      <template #default>
        <p>Unfortunately, at least one input value is invalid.</p>
        <p>Please, Check all inputs!!!</p>
      </template>
      <template #actions>
        <base-button @click="confirmError">Okay</base-button>
      </template>
    </base-dialog>
    <base-card>
      <form @submit.prevent="submitData">
        <div class="form-control">
          <label for="title">Title</label>
          <input type="text" id="title" name="title" v-model="title" />
        </div>
        <div class="form-control">
          <label for="description">Description</label>
          <textarea id="description" name="description" v-model="description">
          </textarea>
        </div>
        <div class="form-control">
          <label for="link">Link</label>
          <input type="url" id="link" name="link" v-model="link" />
        </div>
        <div>
          <base-button type="submit">Add Resource</base-button>
        </div>
      </form>
    </base-card>
  </div>
</template>
<script>
import BaseButton from '../UI/BaseButton.vue';
import BaseDialog from '../UI/BaseDialog.vue';
export default {
  components: { BaseDialog, BaseButton },
  inject: ['addResource'],
  data() {
    return {
      title: '',
      description: '',
      link: '',
      isInvalidValue: false,
    };
  },
  methods: {
    submitData() {
      if (
        this.title.trim() === '' ||
        this.description.trim() === '' ||
        this.link.trim() === ''
      ) {
        this.isInvalidValue = true;
        console.log(this.isInvalidValue);

        return;
      } else {
        this.addResource(this.title, this.description, this.link);
      }
    },
    confirmError() {
      this.isInvalidValue = false;
    },
  },
};
</script>

<style scoped>
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
label {
  margin-right: 0.5rem;
}
</style>
