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
            :class="{active:form.formID==activeForm.formID}"
            v-for="form in forms"
            :key="form.formID"
            @click="setActiveForm(form)"
          >{{form.displayName}}</li>
        </ul>
      </nav>
      <section>
        <table style="width:100%">
          <tr>
            <td style="width:50px;">
              <button class="btnPrev" @click="showPrevForm">&lt;&lt; Prev</button>
            </td>
            <td></td>
            <td style="width:50px;">
              <button class="btnNext" @click="showNextForm">Next &gt;&gt;</button>
            </td>
          </tr>
        </table>
        <hr />
        <component :is="this.activeForm.formName"></component>
        <hr />
        <table style="width:100%">
          <tr>
            <td style="width:50px;">
              <button class="btnPrev" @click="showPrevForm">&lt;&lt; Prev</button>
            </td>
            <td></td>
            <td style="width:50px;">
              <button class="btnNext" @click="showNextForm">Next &gt;&gt;</button>
            </td>
          </tr>
        </table>
      </section>
    </main>
    <footer>footer</footer>
  </div>
</template>

<script>
import OnOffSwitchForm from "./components/vueForms/OnOffSwitchForm";
import HomeForm from "./components/vueForms/HomeForm";
import FormsList from "./forms.json";
export default {
  name: "App",
  components: {
    OnOffSwitchForm: OnOffSwitchForm,
    HomeForm: HomeForm
  },
  data() {
    return {
      isMenuOpen: true,
      forms: FormsList,
      activeForm: FormsList[0]
    };
  },
  methods: {
    ToggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    setActiveForm(frm) {
      this.activeForm = frm;
      window.document.title = "myVueUI:" + frm.displayName;
    },
    showPrevForm() {
      for (let i = 1; i < FormsList.length; i++) {
        if (FormsList[i] == this.activeForm) {
          this.activeForm = FormsList[i - 1];
          break;
        }
      }
    },
    showNextForm() {
      for (let i = 0; i < FormsList.length - 1; i++) {
        if (FormsList[i] == this.activeForm) {
          this.activeForm = FormsList[i + 1];
          break;
        }
      }
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
button {
  padding: 5px 20px;
  border-radius: 5px;
  border: solid 1px;
  white-space: nowrap;
  font-weight: bold;
  cursor: pointer;
  transition: all 200ms;
  box-shadow: 2px 2px 2px black;
}
button:hover {
  background-color: rgba(0, 0, 0, 0.7);
  box-shadow: 1px 1px 4px black;
  color: white;
}
hr {
  margin: 10px 5px;
}
</style>
