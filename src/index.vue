<template>
<div class="st-layout">
  <div class="header">simter-vue-desktop</div>
  <div class="middle">
    <div class="content">
      <st-shortcut
        v-for="(s, index) of shortcuts"
        :key="index"
        :label="s.label"
        :icon="s.icon">
      </st-shortcut>
    </div>
    <div class="sidebar">Sidebar</div>
  </div>
  <div class="footer">©2017 simter-vue-desktop</div>
</div>
</template>

<script>
import stShortcut from "./components/shortcut.vue";

export default {
  data() {
    return {
      test: "test",
      shortcuts: (n => {
        const ss = [];
        for (let i = 0; i < n; i++)
          ss.push({ label: (i < 5 ? `User ${i + 1}` : `User ${i + 1} abc def`), icon: "st-icon-user" });
        return ss;
      })(35)
    };
  },
  components: { stShortcut }
};
</script>

<style>
.st-layout {
  height: 100%;
  display: flex;
  flex-direction: column;
}
.st-layout > .header {
  background-color: #111;
  text-align: center;
  padding: 0.25em;
}
.st-layout > .footer {
  background-color: #111;
  text-align: center;
  padding: 0.25em;
  color: #888;
}
.st-layout > .middle {
  flex-grow: 1;
  display: flex;
  flex-direction: row;
}
.st-layout > .middle > .sidebar {
  min-width: 20em;
  background-color: #111;
}
.st-layout > .middle > .content {
  flex-grow: 1;
  overflow: auto;
  padding-right: .5em;
  padding-bottom: .5em;
}
</style>
