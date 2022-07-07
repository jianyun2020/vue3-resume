<script lang="ts">
import { defineComponent } from "vue";
import Title from "./Title.vue";

export default defineComponent({
  components: {
    Title,
  },
  props: {
    workAndEdu: Object,
  },
});
</script>

<template>
  <Title title-name="工作及教育经历" />
  <div class="content" v-for="item in workAndEdu">
    <div v-if="item.content">
      <div class="title">
        <h2 class="subtitle">{{ item.title }}</h2>
        <span>{{ item.position }}</span>
        <span>{{ item.workTime }}</span>
      </div>
      <p class="detail" v-for="detail in item.content">
        <span v-html="detail"></span>
      </p>
    </div>
    <div v-else>
      <div class="title">
        <h2 class="subtitle">{{ item.title }}</h2>
        <span>{{ item.major }}</span>
        <span>{{ item.type }}</span>
        <span>{{ item.workTime }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.title {
  display: flex;
  justify-content: space-between;
}

.subtitle {
  font-size: 20px;
  font-weight: 600;
  color: #666;
}

span {
  color: #666;
}

.detail {
  color: #666;
}
</style>
