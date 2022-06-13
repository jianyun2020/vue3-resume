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
    <p>
      {{ profile?.gender }} | {{ profile?.age }}岁 | {{ profile?.targetPost }} | 工作年限：{{ profile?.serviceYear }}年
    </p>
    <p>
      手机：{{ profile?.phone }} | 微信：{{ profile?.wechat }} | 邮箱：{{
        profile?.email
      }}
      
    </p>
    <p>
      <a :href="profile?.onlineResume" target="__blank">在线简历：{{ profile?.onlineResume }} </a> | <a :href="profile?.github" target="__blank">Github： {{ profile?.github }}</a>
    </p>
  </div>
</template>

<style scoped>
p {
  color: #666;
}

a {
  color: #666;
  text-decoration: none;
}

</style>
