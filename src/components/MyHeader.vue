<template>
  <div>
    <h1>{{ siteName }}</h1>
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
MyHeader{
  background-color: yellow;
}
h1 {
  text-align: center;
  margin: 0;
  padding: 10px
}
</style>
