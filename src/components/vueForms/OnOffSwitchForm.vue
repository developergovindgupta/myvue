<template>
  <div class="OnOffSwitchForm">
    <div style="text-align:center;">
      <h2 style="color:red;">OnOffSwitch</h2>

      <hr />
    </div>
    <div class="Flex_Table Wrap" style="padding:5px;">
      <div class="Flex_Row">
        <div class="Flex_Cell">
          <h4>Example-1</h4>
        </div>
      </div>
      <div class="Flex_Row">
        <div class="Flex_Cell" width="50%">
          <div class="ExampleCode">
            &lt;template&gt;
            <br />&nbsp; &nbsp; &lt;div id="demo"&gt;
            <br />&nbsp;&nbsp;&nbsp;&nbsp;
            <span
              style="color:red; font-style:italic;"
            >&lt;on-off-switch&gt;&lt;/on-off-switch&gt;</span>
            <br />&nbsp;&nbsp;&lt;/div&gt;
            <br />&lt;/template&gt;
            <br />
            <br />&lt;script&gt;
            <br />import&nbsp;OnOffSwitch&nbsp;from&nbsp;"../vue_ui_components/OnOffSwitch";
            <br />
            <br />export&nbsp;default&nbsp;{
            <br />&nbsp;&nbsp;name:&nbsp;"demo",
            <br />&nbsp;&nbsp;components:&nbsp;{
            <br />&nbsp;&nbsp;&nbsp;&nbsp;OnOffSwitch : OnOffSwitch
            <br />&nbsp;&nbsp;}
            <br />};
            <br />&lt;/script&gt;
          </div>
        </div>
        <div class="Flex_Cell" width="50%">
          <div class="ExampleOutput">
            <on-off-switch></on-off-switch>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import OnOffSwitch from "../vue_ui_components/OnOffSwitch";
export default {
  name: "OnOffSwitchForm",
  components: {
    OnOffSwitch: OnOffSwitch
  },
  props: {
    msg: String
  },
  data() {
    return {
      isOn: false
    };
  }
};
</script>
<style scoped>
/* .OnOffSwitchForm {
  display: block;
} */
</style>
