<template>
<div class="st-shortcut"
  :class="hovering ? hoverClass : ''"
  @mouse-hover="hovering = true"
  @mouse-out="hovering = false">
  <i class="st-shortcut-icon" :class="icon"></i>
  <label class="st-shortcut-label" :title="label">{{label}}</label>
</div>
</template>

<script>
export default {
  props: {
    label: { type: String, require: false },
    icon: { type: String, require: false, default: "st-shortcut-default" },
    value: { require: false },
    hoverable: { type: Boolean, require: false, default: true },
    hoverClass: { type: String, require: false, default: "st-state-hover" }
  },
  data() {
    return { hovering: false };
  }
};
</script>

<style>
.st-shortcut {
  display: inline-block;
  width: 5em;
  margin: 0.5em 0 0 0.5em;
  border: 1px solid transparent;
}
.st-shortcut-icon {
  display: block;
  width: 100%;
  height: 5em;
  background-color: #222;
}
.st-shortcut-label {
  display: block;
  width: 100%;
  text-align: center;
  padding: 0.25em;
  background-color: #333;
  box-sizing: border-box;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
.st-shortcut:hover {
  border: 1px solid gold;
  cursor: pointer;
}
</style>
