<template>
  <div v-if="Solution">
    <h3>Solution Code</h3>
    <hr />
    <div id="code">
      <pre><code>{{ Solution }}</code></pre>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProblemSolution",
  props: {
    Solution: String,
  },
};
</script>

<style scoped>
h3,
#code {
  margin-left: 10px;
  margin-bottom: 0;
}
</style>
