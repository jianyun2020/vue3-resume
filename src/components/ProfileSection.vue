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
        <a :href="profile?.onlineResume">在线简历：{{ profile?.onlineResume }}</a>
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
a {
  color: #666;
  text-decoration: none;
}

@media screen, print and (min-width: 769px) {
  .content {
    font-size: 16px;
  }
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
}

@media print and (max-width: 769px) {
  .content {
    font-size: 16px;
  }
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
}

@media screen and (max-width: 768px) {
  .content {
    font-size: 14px;
  }
  .profile {
    display: flex;
    flex-wrap: wrap;
    color: #666;
    margin: 4px 0;
  }

  .profile li:not(:first-child) {
    position: relative;
  }

  .profile li:not(:first-child)::before {
    content: "|";
    opacity: 0.6;
    margin: 0 4px;
  }
}
</style>
