<template>
  <div class="OnOffSwitchForm">
    <on-off-switch v-model="isOn"></on-off-switch>
    {{isOn}}
  </div>
</template>

<script>
import OnOffSwitch from "../vue_ui_components/OnOffSwitch";
export default {
  name: "OnOffSwitchForm",
  components: {
    OnOffSwitch
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
.OnOffSwitchForm {
  display: block;
}
</style>
