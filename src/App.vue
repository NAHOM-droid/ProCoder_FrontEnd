<template>
  <div class="container">
    <!-- <MyHeader id="header" siteName="ProCoder" yourName="Nahom Demoz" /> -->
    <MyBody id="body" />
    <Editor id="editor" />
    <MyFooter id="footer" />
  </div>
</template>

<script>
// import MyHeader from "./components/MyHeader.vue";
import MyBody from "./components/MyBody.vue";
import MyFooter from "./components/MyFooter.vue";
import Editor from "./components/CodeEditor.vue";

export default {
  name: "App",

  components: {
    // MyHeader,
    MyBody,
    Editor,
    MyFooter,
  },
};
</script>

<style>
body {
  margin: 0;
  padding: 0px;
}
#header {
  grid-area: header;
}

#body {
  grid-area: body;
}

#editor {
  grid-area: editor;
}

#footer {
  grid-area: footer;
}

.container {
  margin: 0;
  padding: 0;
  text-decoration: none;
  box-sizing: border-box;
  background-color: rgb(158, 157, 157);

  display: grid;
  height: 94vh;
  width: 100vw;

  grid-template-columns: 1.5fr 1fr;
  grid-template-rows: 1fr 30px;

  grid-template-areas:
    "body editor"
    "footer footer";
}
</style>
