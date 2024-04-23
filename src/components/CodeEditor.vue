<template>
  <div class="editor-container">
    <div class="editor-header">Code Editor</div>
    <div class="editor">
      <textarea v-model="code"></textarea>
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
  mounted() {
    // Update the textarea height as the content changes
    const codeTextarea = this.$el.querySelector("textarea");
    codeTextarea.style.height = codeTextarea.scrollHeight + "px";
    codeTextarea.addEventListener("input", () => {
      codeTextarea.style.height = "auto";
      codeTextarea.style.height = codeTextarea.scrollHeight + "px";
    });
  },
};
</script>

<style scoped>
.editor-container {
  height: 100vh - 80px;
}

.editor-header {
  padding: 10px;
  background-color: #333;
  color: white;
}

.editor {
  overflow: auto;
  width: 100%;
  height: 100% - 50px;
}

.editor textarea {
  width: 100%;
  height: 100%;
  padding: 10px;
  resize: none;
}
</style>
