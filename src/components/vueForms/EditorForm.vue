<template>
  <div>
    <h1>Editor Demo</h1>
    <editor style="height:400px;" v-model="editorText"></editor>
    <hr />
    <textarea v-model="editorText" style="width:100%; height:300px;"></textarea>
  </div>
</template>

<script>
import editor from "../vue_ui_components/editor";
export default {
  name: "EditorDemoForm",
  components: {
    editor: editor
  },
  data() {
    return {
      editorText: ""
    };
  }
};
</script>
<style scoped>
</style>
