<template>
  <div class="problem" :id="problemId">
    <p>{{ problemId }}. {{ problemCategory }}</p>
  </div>
</template>

<script>
// import SingleProblem from './components/SingleProblem.vue'

export default {
  name: "SingleProblem",
  props: {
    problemId: Number,
    problemCategory: String,
  },
};
</script>

<style scoped>
SingleProblem {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
p{
  padding: 0px;
  margin: 5px;
}
</style>
