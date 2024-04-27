<template>
  <div id="test-cases-box" v-if="Test_Cases">
    <h3>Test Cases</h3>
    <hr>
    <div v-for="test_case of Test_Cases" :key="test_case">
      <div id="test-case">
        <p><strong>Input: </strong> {{ test_case.input }}</p>
        <p><strong>Output: </strong> {{ test_case.output }}</p>
      </div>
      <hr />
    </div>
  </div>
</template>

<script>
export default {
  name: "TestCases",
  props: {
    Test_Cases: Array,
  },
};
</script>

<style scoped>
#test-cases-box {
  overflow-y: auto;
}
h3, #test-case {
  margin-left: 10px;
  margin-bottom: 0;
}

</style>
