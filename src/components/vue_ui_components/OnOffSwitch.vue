<template>
  <label class="OnOffSwitch">
    <span>On-Off-Switch</span>
    <input type="checkbox" class="green tinyswitch" v-model="status" />
    <div>
      <div></div>
    </div>
  </label>
</template>

<script>
export default {
  name: "OnOffSwitch",
  props: {
    value: Boolean
  },
  data() {
    return {
      status: this.value
    };
  },
  watch: {
    status() {
      this.$emit("input", this.status);
    }
  }
};
</script>
<style scoped>
.OnOffSwitch {
  position: relative;
  display: inline-block;
}
.OnOffSwitch span {
  margin-right: 10px;
}
input[type="checkbox"] {
  position: absolute;
  opacity: 0;
}
input[type="checkbox"] + div {
  vertical-align: bottom;
  width: 36px;
  height: 20px;
  border: 1px solid rgba(0, 0, 0, 0.4);
  border-radius: 20px;
  background-color: rgba(0, 0, 0, 0.1);
  transition-duration: 0.4s;
  transition-property: background-color, box-shadow;
  box-shadow: inset 0 0 0 0px rgba(0, 0, 0, 0.4);
  display: inline-block;
}
input[type="checkbox"]:checked + div {
  background-position: 0 0;
  background-color: #00e359;
  border: 1px solid rgba(0, 162, 63, 1);
  box-shadow: inset 0 0 0 10px rgba(0, 227, 89, 1);
}

input[type="checkbox"] + div > div {
  float: left;
  width: 16px;
  height: 16px;
  border-radius: inherit;
  background: #ffffff;
  transition-timing-function: cubic-bezier(0.54, 1.85, 0.5, 1);
  transition-duration: 0.4s;
  transition-property: transform, background-color, box-shadow;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.3), 0px 0px 0 1px rgba(0, 0, 0, 0.4);
  pointer-events: none;
  margin-top: 1px;
  margin-left: 1px;
}
input[type="checkbox"]:checked + div > div {
  transform: translate3d(16px, 0, 0);
  background-color: #ffffff;
  box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.3), 0 0 0 1px rgba(0, 162, 63, 1);
}
</style>
