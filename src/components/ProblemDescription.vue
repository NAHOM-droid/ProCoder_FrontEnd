<template>
  <div id="desc" v-if="Description">
    <h3>{{ title }}</h3>
    <hr />
    <p>{{ Description }}</p>
  </div>
</template>

<script>
export default {
  // Exporting Default Object
  name: "ProblemDescription",
  props: {
    title: String,
    Description: String,
  },
};
</script>

<style scoped>
#desc {
  padding: 0;
  margin: 0;
}
h3,
p {
  margin-left: 10px;
  padding: 0;
  margin-bottom: 0;
}
</style>
