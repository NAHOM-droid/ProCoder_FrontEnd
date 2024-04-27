<template>
  <div>
    <h1 id="pageName">{{ siteName }}</h1>
    <!-- <p>by {{ yourName }}</p> -->
  </div>
</template>

<script>
export default {
  name: "MyHeader",
  props: {
    siteName: String,
    yourName: String,
  },
};
</script>

<style scoped>
#pageName {
  margin: 0;
  padding: 10px;
  padding-left: 20px;
}
</style>
