<script lang="ts">
import data from "./data/data.json";
import { defineComponent } from "vue";
import ProfileSection from "./components/ProfileSection.vue";
import WorkAndEduSection from "./components/workAndEduSection.vue";
import ProjectSection from "./components/ProjectSection.vue";


export default defineComponent({
  components: {
    ProfileSection,
    WorkAndEduSection,
    ProjectSection,
  },
  data() {
    return {
      data: data,
    };
  },
});
</script>

<template>
  <ProfileSection :profile="data.profile" />
  <WorkAndEduSection :workAndEdu="data.workAndEdu" />
  <ProjectSection classification="项目经历" :project="data.project" />
  <ProjectSection classification="开源项目" :project="data.openSource" />
  <ProjectSection classification="常用技术栈" :project="data.technologyStack" />
</template>

<style>
* {
  margin: 0;
  padding: 0;
}
body {
  background-color: #eee;
  margin: 20px 0;
}

p {
  margin: 10px 0;
}

#app {
  font-family: "Microsoft YaHei";
  width: 21cm;
  min-height: 29.7cm;
  margin: 0 auto;
  overflow: auto;
  padding: 1em;
  background-color: #fff;
  margin: 0 auto;
}

.content {
  margin: 14px;
}

i {
  padding: 2px;
  font-weight: 580;
  /* PDF使用 */
  color: #333; 
  /* 网页使用 */
  color: #FF6600;
  font-style: normal;
}
</style>
