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
  <div class="footer">
    <div class="copyright">©2017 simter-vue-desktop</div>
    <div class="toggler"></div>
    <div class="tasks-bar">
      <st-task
        v-for="(s, index) of tasks"
        :key="index"
        :label="s.label"
        :icon="s.icon">
      </st-task>
    </div>
  </div>
</div>
</template>

<script>
import stShortcut from "./components/shortcut.vue";
import stTask from "./components/task.vue";

export default {
  data() {
    return {
      test: "test",
      shortcuts: (n => {
        const ss = [];
        for (let i = 0; i < n; i++)
          ss.push({ label: (i < 5 ? `User ${i + 1}` : `User ${i + 1} abc def`), icon: "st-icon-user" });
        return ss;
      })(35),
      tasks: (n => {
        const ss = [];
        for (let i = 0; i < n; i++)
          ss.push({ label: (i < 5 ? `User ${i + 1}` : `User ${i + 1} abc def`), icon: "st-icon-user" });
        return ss;
      })(6)
    };
  },
  components: { stShortcut, stTask }
};
</script>

<style>
.st-layout {
  height: 100%;
  display: flex;
  flex-direction: column;
}
.st-layout > .header {
  position: relative;
  background-color: #111;
  text-align: center;
  padding: 0.25em;
  border-bottom: 1px solid #222;
}
.st-layout > .footer {
  position: relative;
  background-color: #111;
  min-height: 2.5em;
  border-top: 1px solid #222;
}
.st-layout > .footer > .copyright {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  text-align: center;
  padding: 0.25em;
  color: #888;
}
.st-layout > .footer > .toggler {
  position: absolute;
  border-left: 1px solid #222;
  bottom: 0;
  top: 0;
  right: 0;
  width: 10px;
}
.st-layout > .footer > .tasks-bar {
  padding: 0.25em;
}

.st-layout > .middle {
  flex-grow: 1;
  display: flex;
  flex-direction: row;
}
.st-layout > .middle > .sidebar {
  position: relative;
  min-width: 20em;
  background-color: #111;
}
.st-layout > .middle > .content {
  position: relative;
  flex-grow: 1;
  overflow: auto;
  padding-right: .5em;
  padding-bottom: .5em;
  border-right: 1px solid #222;
}
</style>
