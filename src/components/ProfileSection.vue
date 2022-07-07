<script lang="ts">
import { defineComponent } from "vue";
import Title from "./Title.vue";

export default defineComponent({
  components: {
    Title,
  },
  props: {
    profile: Object,
  },
});
</script>

<template>
  <Title :title-name="profile?.name" />
  <div class="content">
    <ul class="profile">
      <li>{{ profile?.gender }}</li>
      <li>{{ profile?.age }}岁</li>
      <li>{{ profile?.targetPost }}</li>
      <li>
        <a :href="profile?.targetPost">在线简历：{{ profile?.onlineResume }}</a>
      </li>
    </ul>
    <ul class="profile">
      <li>手机：{{ profile?.phone }}</li>
      <li>微信：{{ profile?.wechat }}</li>
      <li>邮箱：{{ profile?.email }}</li>
    </ul>
  </div>
</template>

<style scoped>
.profile {
  display: flex;
  flex-wrap: wrap;
  color: #666;
  margin: 8px 0;
}

.profile li:not(:first-child) {
  position: relative;
}

.profile li:not(:first-child)::before {
  content: "|";
  opacity: 0.6;
  margin: 0 8px;
}

a {
  color: #666;
  text-decoration: none;
}
</style>
