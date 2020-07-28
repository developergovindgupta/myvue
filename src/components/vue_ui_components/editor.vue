<template>
  <div class="editor">
    <div class="editorMenuBar">
      <a class="cmdButton Bold" title="Bold" @mousedown.stop.prevent="cmdBold">
        <svg version="1.1" width="12" height="12" viewBox="0 0 16 16">
          <path
            fill="#000000"
            d="M11.061 7.573c0.586-0.696 0.939-1.594 0.939-2.573 0-2.206-1.794-4-4-4h-5v14h6c2.206 0 4-1.794 4-4 0-1.452-0.778-2.726-1.939-3.427zM6 3h1.586c0.874 0 1.586 0.897 1.586 2s-0.711 2-1.586 2h-1.586v-4zM8.484 13h-2.484v-4h2.484c0.913 0 1.656 0.897 1.656 2s-0.743 2-1.656 2z"
          />
        </svg>
      </a>
      <a class="cmdButton Italic" title="Italic" @mousedown.stop.prevent="cmdItalic">
        <svg version="1.1" width="16" height="16" viewBox="0 0 16 16">
          <path fill="#000000" d="M14 1v1h-2l-5 12h2v1h-7v-1h2l5-12h-2v-1z" />
        </svg>
      </a>
      <a class="cmdButton Underline" title="Underline" @mousedown.stop.prevent="cmdUnderline">
        <svg version="1.1" width="16" height="16" viewBox="0 0 16 16">
          <path
            fill="#000000"
            d="M11 1h2v6.5c0 2.485-2.239 4.5-5 4.5s-5-2.015-5-4.5v-6.5h2v6.5c0 0.628 0.285 1.23 0.802 1.695 0.577 0.519 1.357 0.805 2.198 0.805s1.621-0.286 2.198-0.805c0.517-0.466 0.802-1.068 0.802-1.695v-6.5zM3 13h10v2h-10z"
          />
        </svg>
      </a>
      <a class="cmdButton Cut" title="Cut" @mousedown.stop.prevent="cmdCut">
        <svg version="1.1" width="16" height="16" viewBox="0 0 16 16">
          <path
            fill="#000000"
            d="M14.279 10.62c-1.042-1.628-2.829-2.345-3.992-1.601-0.1 0.064-0.193 0.138-0.277 0.218l-1.241-1.942 2.867-4.5c0.235-0.433 0.321-0.949 0.207-1.468-0.109-0.496-0.383-0.913-0.752-1.207l-0.192-0.122-3.398 5.314-3.398-5.314-0.192 0.122c-0.369 0.294-0.643 0.711-0.752 1.207-0.114 0.519-0.027 1.035 0.207 1.468l2.867 4.5-1.241 1.942c-0.085-0.081-0.177-0.154-0.277-0.218-1.163-0.744-2.95-0.028-3.992 1.601s-0.944 3.551 0.219 4.296c1.163 0.744 2.95 0.028 3.992-1.601l2.567-4.029 2.567 4.029c1.042 1.628 2.829 2.345 3.992 1.601s1.261-2.667 0.219-4.296zM3.67 12.507c-0.469 0.733-1.071 1.089-1.478 1.179-0 0-0 0-0 0-0.133 0.029-0.317 0.047-0.443-0.033-0.139-0.089-0.231-0.324-0.247-0.629-0.025-0.494 0.151-1.076 0.483-1.594 0.469-0.733 1.071-1.089 1.478-1.179 0.133-0.029 0.317-0.047 0.443 0.033 0.139 0.089 0.231 0.324 0.247 0.629 0.025 0.495-0.151 1.076-0.483 1.594zM7.5 8c-0.276 0-0.5-0.224-0.5-0.5s0.224-0.5 0.5-0.5 0.5 0.224 0.5 0.5-0.224 0.5-0.5 0.5zM13.498 13.023c-0.016 0.305-0.108 0.54-0.247 0.629-0.125 0.080-0.31 0.062-0.443 0.033 0 0 0 0-0 0-0.407-0.089-1.009-0.446-1.478-1.179-0.332-0.519-0.508-1.1-0.483-1.594 0.016-0.305 0.108-0.54 0.247-0.629 0.125-0.080 0.31-0.062 0.443-0.033 0.407 0.089 1.009 0.446 1.478 1.179 0.332 0.519 0.508 1.1 0.483 1.594z"
          />
        </svg>
      </a>
      <a class="cmdButton Copy" title="Copy" @mousedown.stop.prevent="cmdCopy">
        <svg version="1.1" width="16" height="16" viewBox="0 0 16 16">
          <path
            fill="#000000"
            d="M10 4v-4h-7l-3 3v9h6v4h10v-12h-6zM3 1.414v1.586h-1.586l1.586-1.586zM1 11v-7h3v-3h5v3l-3 3v4h-5zM9 5.414v1.586h-1.586l1.586-1.586zM15 15h-8v-7h3v-3h5v10z"
          />
        </svg>
      </a>
      <a class="cmdButton Paste" title="Paste" @mousedown.stop.prevent="cmdPaste">
        <svg version="1.1" width="16" height="16" viewBox="0 0 16 16">
          <path
            fill="#000000"
            d="M11 2h-2v-1c0-0.55-0.45-1-1-1h-2c-0.55 0-1 0.45-1 1v1h-2v2h8v-2zM8 2h-2v-0.998c0.001-0.001 0.001-0.001 0.002-0.002h1.996c0.001 0.001 0.001 0.001 0.002 0.002v0.998zM13 5v-2.5c0-0.275-0.225-0.5-0.5-0.5h-1v1h0.5v2h-3l-3 3v4h-4v-9h0.5v-1h-1c-0.275 0-0.5 0.225-0.5 0.5v10c0 0.275 0.225 0.5 0.5 0.5h4.5v3h10v-11h-3zM9 6.414v1.586h-1.586l1.586-1.586zM15 15h-8v-6h3v-3h5v9z"
          />
        </svg>
      </a>
      <a class="cmdButton JustifyLeft" title="Align Left" @mousedown.stop.prevent="cmdAlignLeft">
        <svg version="1.1" width="16" height="16" viewBox="0 0 16 16">
          <path
            fill="#000000"
            d="M0 1h16v2h-16zM0 4h10v2h-10zM0 10h10v2h-10zM0 7h16v2h-16zM0 13h16v2h-16z"
          />
        </svg>
      </a>
      <a
        class="cmdButton JustifyCenter"
        title="Align Center"
        @mousedown.stop.prevent="cmdAlignCenter"
      >
        <svg version="1.1" width="16" height="16" viewBox="0 0 16 16">
          <path
            fill="#000000"
            d="M0 1h16v2h-16zM3 4h10v2h-10zM3 10h10v2h-10zM0 7h16v2h-16zM0 13h16v2h-16z"
          />
        </svg>
      </a>
      <a class="cmdButton JustifyRight" title="Align Right" @mousedown.stop.prevent="cmdAlignRight">
        <svg version="1.1" width="16" height="16" viewBox="0 0 16 16">
          <path
            fill="#000000"
            d="M0 1h16v2h-16zM6 4h10v2h-10zM6 10h10v2h-10zM0 7h16v2h-16zM0 13h16v2h-16z"
          />
        </svg>
      </a>
      <a class="cmdButton outdent" title="Outdent" @mousedown.stop.prevent="cmdOutdent">
        <svg version="1.1" width="16" height="16" viewBox="0 0 16 16">
          <path
            fill="#000000"
            d="M0 1h16v2h-16zM6 4h10v2h-10zM6 7h10v2h-10zM6 10h10v2h-10zM0 13h16v2h-16zM4 5v6l-4-3z"
          />
        </svg>
      </a>
      <a class="cmdButton indent" title="Indent" @mousedown.stop.prevent="cmdIndent">
        <svg version="1.1" width="16" height="16" viewBox="0 0 16 16">
          <path
            fill="#000000"
            d="M0 1h16v2h-16zM6 4h10v2h-10zM6 7h10v2h-10zM6 10h10v2h-10zM0 13h16v2h-16zM0 11v-6l4 3z"
          />
        </svg>
      </a>
      <a
        class="cmdButton removeFormat"
        title="Remove Formatting"
        @mousedown.stop.prevent="cmdRemoveFormat"
      >
        <svg version="1.1" width="16" height="16" viewBox="0 0 16 16">
          <path
            fill="#000000"
            d="M0 14h9v2h-9zM14 2h-4.727l-2.871 11h-2.067l2.871-11h-4.205v-2h11zM14.528 16l-2.028-2.028-2.028 2.028-0.972-0.972 2.028-2.028-2.028-2.028 0.972-0.972 2.028 2.028 2.028-2.028 0.972 0.972-2.028 2.028 2.028 2.028z"
          />
        </svg>
      </a>
    </div>
    <div class="editorBody" contenteditable="true" v-html="html" @input="editorChange"></div>
  </div>
</template>

<script>
export default {
  name: "editor",
  props: {
    value: {
      type: String,
      default: ""
    }
  },
  data() {
    return {
      html: this.value
    };
  },
  methods: {
    editorChange(e) {
      this.$emit("input", e.target.innerHTML);
    },
    cmdBold() {
      document.execCommand("bold", false, null);
    },
    cmdItalic() {
      document.execCommand("italic", false, null);
    },
    cmdUnderline() {
      document.execCommand("underline", false, null);
    },
    cmdCut() {
      document.execCommand("cut", false, null);
    },
    cmdCopy() {
      document.execCommand("copy", false, null);
    },
    cmdPaste() {
      document.execCommand("paste", false, null);
    },
    cmdAlignLeft() {
      document.execCommand("justifyLeft", false, null);
    },
    cmdAlignCenter() {
      document.execCommand("justifyCenter", false, null);
    },
    cmdAlignRight() {
      document.execCommand("justifyRight", false, null);
    },
    cmdOutdent() {
      document.execCommand("outdent", false, null);
    },
    cmdIndent() {
      document.execCommand("indent", false, null);
    },
    cmdRemoveFormat() {
      document.execCommand("removeFormat", false, null);
    }
  }
};
</script>
<style scoped>
.editor {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 100%;
  overflow: hidden;
  padding: 2px;
  border: solid 1px black;
  background-color: gray;
}
.editor .editorMenuBar {
  display: flex;
  flex-grow: 0;
  flex-shrink: 0;
  background-color: rgba(0, 0, 0, 0.5);
  border: solid 1px black;
  padding: 2px;
  border-radius: 3px 3px 0 0;
}
.editor .editorBody {
  background-color: white;
  color: black;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 10pt;
  padding: 10px;
  border: solid 1px black;
  border-radius: 0 0 3px 3px;
  flex-grow: 1;
  flex-shrink: 1;
  min-height: 100px;

  overflow: auto;
}
.editor .editorMenuBar .cmdButton {
  background-color: rgba(255, 255, 255, 0.5);
  color: black;
  padding: 3px;
  margin: 1px;
  border-radius: 3px;
  line-height: 0em;
  cursor: pointer;
  transition: all 200ms;
  box-shadow: inset 0px 0px 2px 0px black;
  border: solid 1px rgba(0, 0, 0, 0.8);
}
.editor .editorMenuBar .cmdButton:hover {
  background-color: rgba(255, 255, 255, 0.7);
}
.editor .editorMenuBar .cmdButton svg {
  width: 14px;
  height: 14px;
}
</style>
