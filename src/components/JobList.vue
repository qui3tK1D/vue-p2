<template>
  <li @dblclick="toggleInput">
    <button @click="deleteList">Del</button> &nbsp;

    <input
      type="text"
      v-if="isEdit"
      v-model="inputText"
      @keyup.enter="updateJob"
    />
    <span v-else>{{ list.job }}</span>
  </li>
</template>

<script>
export default {
  props: ["list"],
  data() {
    return {
      isEdit: false,
      inputText: this.list.job,
    };
  },
  methods: {
    toggleInput() {
      this.isEdit = !this.isEdit;
    },

    updateJob() {
      this.toggleInput();
      this.$emit("updateList", this.list, this.inputText);
      // console.log(this.inputText);
    },

    deleteList() {
      // console.log(this.list.id);
      this.$emit("delList", this.list.id);
      // console.log(this.list);
    },
  },
};
</script>

<style scoped>
li {
  margin-bottom: 0.5rem;
}
</style>

<!-- -->
