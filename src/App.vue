<script lang="ts">
import data from "./data/data.json";
import { defineComponent } from "vue";
import ProfileSection from "./components/ProfileSection.vue";
import WorkAndEduSection from "./components/workAndEduSection.vue";
import ProjectSection from "./components/ProjectSection.vue";
import OpenSource from "./components/OpenSource.vue";

export default defineComponent({
  components: {
    ProfileSection,
    WorkAndEduSection,
    ProjectSection,
    OpenSource,
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
  <OpenSource classification="开源项目" :project="data.openSource" />
  <OpenSource classification="常用技术栈" :project="data.technologyStack" />
</template>

<style>
* {
  margin: 0;
  padding: 0;
}
ul,
li {
  list-style: none;
}
@media screen, print and (min-width: 769px) {
  body {
    background-color: #eee;
    margin: 20px 0;
  }

  p {
    margin: 5px 0;
  }

  #app {
    font-family: "Microsoft YaHei";
    width: 21cm;
    min-height: 29.7cm;
    margin: 0 auto;
    overflow: auto;
    padding: 1em;
    background-color: #fff;
  }

  .content {
    margin: 10px;
  }

  i {
    padding: 2px;
    font-weight: 580;
    /* PDF使用 */
    color: #333;
    /* 网页使用 */
    color: #ff6600;
    font-style: normal;
  }
}

@media print and (max-width: 769px) {
  body {
    background-color: #eee;
    margin: 20px 0;
  }

  p {
    margin: 5px 0;
  }

  #app {
    font-family: "Microsoft YaHei";
    width: 21cm;
    min-height: 29.7cm;
    margin: 0 auto;
    overflow: auto;
    padding: 1em;
    background-color: #fff;
  }

  .content {
    margin: 10px;
  }

  i {
    padding: 2px;
    font-weight: 580;
    /* PDF使用 */
    color: #333;
    /* 网页使用 */
    color: #ff6600;
    font-style: normal;
  }
}

@media screen and (max-width: 768px) {
  #app {
    box-sizing: border-box;
    width: 100vw;
    padding: 10px;
    background-color: #fff;
  }

  .content {
    margin: 4px;
  }

  i {
    padding: 2px;
    font-weight: 580;
    /* PDF使用 */
    color: #333;
    /* 网页使用 */
    color: #ff6600;
    font-style: normal;
  }
}
</style>
