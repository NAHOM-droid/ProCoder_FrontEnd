<template>
  <div class="container">
    <nav id="nav">
      <button>ProCoder</button>
      <button id="button" @click="handleClick('all')">All</button>
      <button id="button" @click="handleClick('description')">
        Problem-Desc
      </button>
      <button id="button" @click="handleClick('hint')">Hint</button>
      <button id="button" @click="handleClick('testcases')">Test Cases</button>
      <button id="button" @click="handleClick('solution')">
        Solution-Code
      </button>
    </nav>
    <div id="left-comp">
      <ProblemList @updateProblemComponents="updateComponents" />
    </div>
    <div id="center-comps">
      <Description
        v-show="isComponentVisible('description')"
        :Description="currentDescription"
        :title="currentTitle"
      />
      <Hint v-show="isComponentVisible('hint')" :Hint="currentHint" />
      <TestCases
        v-show="isComponentVisible('testcases')"
        :Test_Cases="currentTestCases"
      />
      <Solution
        v-show="isComponentVisible('solution')"
        :Solution="currentSolution"
      />
    </div>
  </div>
</template>

<script>
import ProblemList from "./ProblemList.vue";
import Description from "./ProblemDescription.vue";
import Hint from "./ProblemHint.vue";
import Solution from "./ProblemSolution.vue";
import TestCases from "./TestCases.vue";

export default {
  name: "MyBody",
  components: {
    ProblemList,
    Description,
    Hint,
    Solution,
    TestCases,
  },
  data() {
    return {
      currentTitle: "",
      currentDescription: "",
      currentHint: "",
      currentTestCases: "",
      currentSolution: "",
      activeComponent: "all",
    };
  },
  methods: {
    updateComponents(problem) {
      this.currentTitle = problem.Id + ". " + problem.Category;
      this.currentDescription = problem.Description;
      this.currentHint = problem.Hint;
      this.currentTestCases = problem.TestCases;
      this.currentSolution = problem.Solution_Code;
      this.activeComponent = "all";
    },
    handleClick(componentName) {
      this.activeComponent = componentName;
    },
    isComponentVisible(param) {
      return this.activeComponent === param || this.activeComponent === "all";
    },
  },
};
</script>

<style scoped>
#nav {
  grid-area: nav;
  padding: 0;
  margin: 0;
  display: flex;
  background-color: #8ab3b3;
}

#button, button {
  border: none;
  background-color: transparent;
  padding: 0 5px;
  margin-left: 20px;
  color: black;
  cursor: pointer;
  font-size: 15px;
}

#button:hover {
  background-color: #bebfc0; /* Change button background color on hover */
}

#left-comp {
  grid-area: pro-list;
  padding-left: 10px;
  background-color: rgb(122, 120, 120);
  overflow-y: scroll;
  scrollbar-width: none;
}

#center-comps {
  overflow: scroll;
  scrollbar-width: none;
  grid-area: center-comps;
  background-color: rgb(122, 120, 120);
}

.container {
  margin: 0;
  padding: 0;
  text-decoration: none;
  box-sizing: border-box;

  display: grid;
  /* height: 100%; */
  width: 100%;

  grid-template-columns: 0.5fr 1fr;
  grid-template-rows: 40px 1fr;

  grid-template-areas:
    "nav nav"
    "pro-list center-comps";

  column-gap: 0.2rem;
}
</style>
