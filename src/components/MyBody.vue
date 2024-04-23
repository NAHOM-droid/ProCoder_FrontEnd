<template>
  <div class="container">
    <nav>
      <button @click="handleClick('description')">Problem-Desc</button>
      <button @click="handleClick('hint')">Hint</button>
      <button @click="handleClick('testcases')">Test Cases</button>
      <button @click="handleClick('solution')">Solution-Code</button>
    </nav>
    <div id="left-comp">
      <ProblemList @updateProblemComponents="updateComponents" />
    </div>
    <div id="center-comps">
      <Description
        v-show="activeComponent === 'description'"
        :Description="currentDescription" :title="currentTitle"
      />
      <Hint v-show="activeComponent === 'hint'" :Hint="currentHint" />
      <TestCases
        v-show="activeComponent === 'testcases'"
        :Test_Cases="currentTestCases"
      />
      <Solution
        v-show="activeComponent === 'solution'"
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
      activeComponent: "description", // Default to description component
    };
  },
  methods: {
    updateComponents(problem) {
      this.currentTitle = problem.Id + ". " + problem.Category;
      this.currentDescription = problem.Description;
      this.currentHint = problem.Hint;
      this.currentTestCases = problem.TestCases;
      this.currentSolution = problem.Solution_Code;
      this.activeComponent = "description"; // Show description component after update
    },
    handleClick(componentName) {
      this.activeComponent = componentName;
    },
  },
};
</script>

<style scoped>
nav {
  grid-area: nav;
  padding: 0;
  margin: 0;
  display: flex;
  background-color: #8ab3b3;
}

button {
  border: none;
  background-color: transparent;
  padding: 0 5px;
  margin-left: 20px;
  color: black;
  cursor: pointer;
  font-size: 15px;
}

button:hover {
  background-color: #bebfc0; /* Change button background color on hover */
}

#left-comp {
  overflow-y: auto;
  height: 97%;
  grid-area: pro-list;
  padding-left: 10px;
}
#right-comp {
  grid-area: editor;
  height: 97%;
  overflow: scroll;
}

#center-comps {
  overflow: auto;
  height: 100%;
  grid-area: center-comps;
}

.container {
  margin: 0;
  padding: 0;
  text-decoration: none;
  box-sizing: border-box;

  display: grid;
  height: 100vh-80px;
  width: 100%;

  grid-template-columns: 0.5fr 1fr;
  grid-template-rows: 40px 1fr;

  grid-template-areas:
    "nav nav"
    "pro-list center-comps";

  column-gap: 0.2rem;
}
</style>

<!-- .container {
  display: flex;
  /* align-items: center; */
  width: 100%;
  height: 100%;
}

.left-comp {
  flex: 1;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  overflow-y: auto;
  height: 100%;
}
.right-comp {
  flex: 2; /* Makes left and right divs take up equal space */
  padding: 1rem; /* Add padding for spacing */
}

.center-comps {
  display: flex;
  flex-direction: column;
  flex: 2;
  overflow: hidden;
  height: 100%;
}

.center-comps {
  padding: 1rem;
  /* text-align: center; //Center text in center divs */
}

/* .center-comp:not(.active) {
  display: hidden;
  transition: opacity 0.5s ease-in-out;
}

.center-comp.active {
  display: block;
} */ -->
