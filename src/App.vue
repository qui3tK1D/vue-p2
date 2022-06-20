<template>
  <CardTitle :header="title" />
  <ul>
    <JobList
      v-for="list in lists"
      :key="list.id"
      :list="list"
      @delList="delList"
      @updateList="updateList"
    />
  </ul>
</template>

<script>
import CardTitle from "./components/CardTitle.vue";
import JobList from "./components/JobList.vue";
export default {
  name: "App",
  components: { CardTitle, JobList },
  data() {
    return {
      title: "Job Lists",
      lists: [
        {
          id: "1",
          job: "to eat",
        },
        {
          id: "2",
          job: "to sleep",
        },
        {
          id: "3",
          job: "to drink",
        },
      ],
    };
  },
  methods: {
    delList(id) {
      this.lists = this.lists.filter((cur) => cur.id !== id);
    },
    updateList(updateList, newJob) {
      const updatedListIndex = this.lists.findIndex(
        (cur) => cur.id === updateList.id
      );
      this.lists[updatedListIndex].job = newJob;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
