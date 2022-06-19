<template>
  <CardTitle :header="title" />
  <ul>
    <JobList v-for="{ id, job } in lists" :key="id" :job="job" />
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
