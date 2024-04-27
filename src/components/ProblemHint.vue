<template>
  <div v-if="Hint">
    <h3>Hint</h3>
    <hr />
    <p>{{ Hint }}</p>
  </div>
</template>

<script>
export default {
  // Exporting Default Object
  name: "ProblemHint",
  props: {
    Hint: String,
  },
};
</script>

<style scoped>
h3,
p {
  margin-left: 10px;
  margin-bottom: 0;
}
</style>
