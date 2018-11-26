<template>
<div class="st-task"
  :class="hovering ? hoverClass : ''"
  :title="label"
  @mouse-hover="hovering = true"
  @mouse-out="hovering = false">
  <i class="st-task-icon" :class="icon"></i>
  <label class="st-task-label">{{label}}</label>
</div>
</template>

<script>
export default {
  props: {
    label: { type: String, require: false },
    icon: { type: String, require: false, default: "st-task-default" },
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
.st-task {
  display: inline-flex;
  flex-direction: row;
  margin-right: 0.25em;
  max-width: 5em;
  border: 1px solid transparent;
  background-color: #222;
}
.st-task-icon {
  font-style: normal;
  width: 1em;
}
.st-task-label {
  flex-grow: 1;
  min-width: 2em;
  padding: 0.25em;
  background-color: #222;
  box-sizing: border-box;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
.st-task:hover {
  border: 1px solid gold;
  cursor: pointer;
}
</style>
