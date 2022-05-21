<script lang="ts">
import { defineComponent } from "vue";
import QrcodeVue from 'qrcode.vue'

import Title from "./Title.vue";

export default defineComponent({
  components: {
    Title,
    QrcodeVue
  },
  props: {
    project: Object,
    classification: String
  },
});
</script>

<template>
  <Title :title-name="classification" />
  <div class="content" v-for="item in project">
      <div class="title">
        <h2 class="subtitle">{{ item.title }}</h2>
      </div>
    <div class="sub-content">
      <div>
        <p class="detail" v-for="detail in item.content">
          <p v-html="detail"></p>
        </p>
      </div>
      <div v-if="item.link">
        <a :href="item.link" target="__blank">
          <QrcodeVue class="qrcode" :value="item.link" />
        </a>
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
  font-size: 18px;
  font-weight: 600;
  color: #666;
}

.sub-content {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}

.detail {
  color: #666;
}
a {
  position: relative;
}

.qrcode {
  width: 100px;
  height: 100px;
  cursor: pointer;
  margin: 10px 0;
}

a::after {
  content: '点击打开链接';
  position: absolute;
  top: 95%;
  left: 0;
  width: 100%;
  font-size: 12px;
  text-align: center;
  color: #666;
}

</style>
