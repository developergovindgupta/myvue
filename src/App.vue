<template>
  <div id="app">
    <header>
      <div class="navButton" @click="ToggleMenu">
        <div></div>
        <div></div>
        <div></div>
        <div></div>
      </div>
      <svg width="30" height="30" viewBox="0 0 256 221" preserveAspectRatio="xMinYMin meet">
        <path d="M204.8 0H256L128 220.8 0 0h97.92L128 51.2 157.44 0h47.36z" fill="#41B883" />
        <path d="M0 0l128 220.8L256 0h-51.2L128 132.48 50.56 0H0z" fill="#41B883" />
        <path d="M50.56 0L128 133.12 204.8 0h-47.36L128 51.2 97.92 0H50.56z" fill="#35495E" />
      </svg>
      <span>Welcome in myVueUI Template Collections</span>
    </header>
    <main>
      <nav :class="{open:isMenuOpen}">
        <ul>
          <li
            :class="{active:form.formID==activeFormID}"
            v-for="form in forms"
            :key="form.formID"
            @click="setActiveForm(form)"
          >{{form.displayName}}</li>
        </ul>
      </nav>
      <section>
        <on-off-switch-form v-if="activeFormID==1"></on-off-switch-form>
      </section>
    </main>
    <footer>footer</footer>
  </div>
</template>

<script>
import OnOffSwitchForm from "./components/vueForms/OnOffSwitchForm";
export default {
  name: "App",
  components: {
    OnOffSwitchForm: OnOffSwitchForm
  },
  data() {
    return {
      isMenuOpen: true,
      activeFormID: 0,
      forms: [
        {
          formID: 0,
          formName: "homeForm",
          displayName: "Home"
        },
        {
          formID: 1,
          formName: "OnOffSwitchForm",
          displayName: "OnOffSwitch"
        }
      ]
    };
  },
  methods: {
    ToggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    setActiveForm(frm) {
      this.activeFormID = frm.formID;
      window.document.title = "myVueUI:" + frm.displayName;
    }
  }
};
</script>
<style>
@import "./assets/style.css";
</style>
<style scopped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
.navButton {
  display: inline-block;
  width: 25px;
  height: 30px;
  padding: 2px;
  border: solid 1px black;
  background-color: rgba(0, 0, 0, 0.6);
  margin: 1px 3px 1px 0px;
  cursor: pointer;
}
.navButton div {
  padding: 1px;
  margin: 3px 0px;
  background-color: white;
}
</style>
