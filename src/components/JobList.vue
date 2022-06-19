<template>
  <li @dblclick="toggleInput">
    <input
      type="text"
      v-if="isEdit"
      v-model="inputText"
      ref="input"
      @keyup.enter="updateJob"
    />
    <span v-else>{{ job }}</span>
  </li>
</template>

<script>
export default {
  props: ["job"],
  data() {
    return {
      isEdit: false,
      inputText: this.job,
    };
  },
  methods: {
    toggleInput() {
      this.isEdit = !this.isEdit;
    },

    updateJob() {
      this.toggleInput();
      console.log("success");
    },
  },
};
</script>

<style></style>

<!-- -->
