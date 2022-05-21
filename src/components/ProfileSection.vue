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
      {{ profile?.gender }} | {{ profile?.age }}岁 | {{ profile?.targetPost }}
    </p>
    <p>
      手机：{{ profile?.phone }} | 微信：{{ profile?.wechat }} | 邮箱：{{
        profile?.email
      }}
      | 工作年限：{{ profile?.serviceYear }}年
    </p>
  </div>
</template>

<style scoped>
p {
  color: #666;
}

</style>
