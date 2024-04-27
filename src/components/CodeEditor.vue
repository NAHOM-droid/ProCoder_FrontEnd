<template>
  <div class="editor-container">
    <div class="editor-header">Code Editor</div>
    <div class="editor">
      <textarea id="text-area" v-model="code"></textarea>
    </div>
  </div>
</template>

<script>
export default {
  name: "CodeEditor",
  data() {
    return {
      code: `// Welcome to Code Editor\n\nfunction greet() {\n  return 'Hello, World!';\n}\n\nconsole.log(greet());`,
    };
  },
};
</script>

<style scoped>
.editor-container {
  height: 100%;
  background-color: white;
}

.editor-header {
  padding: 10px;
  background-color: #333;
  color: white;
}

.editor {
  width: 100%;
  height: 92%;
}

.editor #text-area {
  width: 95%;
  padding-left: 10px;
  height: 100%;
  resize: none;
  overflow-y: scroll;
  scrollbar-width: thin;
}
</style>
