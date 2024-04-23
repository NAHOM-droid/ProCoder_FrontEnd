<template>
  <footer>
    <div>
      <a href="">All RighRights Reserved</a>
      <a href="https://www.github.com">GitHub</a>
      <a href="https://www.linkedin.com">LinkedIn</a>
      <a href="https://www.facebook.com">Facebook</a>
      <a href="https://www.instagram.com">Instagram</a>
    </div>
  </footer>
</template>

<script>
export default {
  name: "MyFooter",
  props: {
    siteName: String,
  },
};
</script>

<style scoped>
footer {
  display: block;
  color: white;
  background-color: black;
  text-align: center;
  margin: 0;
  padding: 5px;
  box-sizing: border-box;
  text-decoration: none;
  justify-content: space-between;
  width: 100vw;
}

footer a {
  text-decoration: none;
  color: azure;
  justify-content: space-between;
  padding: 14px;
}
</style>
