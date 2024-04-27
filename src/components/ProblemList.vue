<template>
  <div
    id="list-div"
    v-for="problem in problems"
    :key="problem.Id"
    @click="SelectedProblem(problem)"
  >
    <SingleProblem
      :problemId="problem.Id"
      :problemCategory="problem.Category"
    />
  </div>
</template>

<script>
import SingleProblem from "./SingleProblem.vue";

export default {
  name: "ProblemList",
  components: {
    SingleProblem,
  },
  data() {
    return {
      problems: [],
    };
  },
  methods: {
    async fetchProblems() {
      const res = await fetch("https://procoder-backend.onrender.com/api");
      const data = await res.json();

      // default problem choosen
      this.SelectedProblem(data[0]);
      return data;
    },
    SelectedProblem(problem) {
      // Emit an event to the parent component to update the contents of the current problem
      this.$emit("updateProblemComponents", problem);
    },
  },
  async created() {
    this.problems = await this.fetchProblems();
  },
};
</script>

<style scoped>
#list-div {
  margin: 0;
  margin-top: 10px;
  padding: 0;
  box-sizing: border-box;
  overflow-y: auto;
}
</style>
