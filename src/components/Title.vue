<script lang="ts">
// defineProps<{ titleName: string }>()
export default {
  props: {
    titleName: String,
  },
};
</script>

<template>
  <h1 class="title">{{ titleName }}</h1>
</template>

<style scoped>
@media screen, print and (min-width: 769px) {
  .title {
    position: relative;
    font-size: 24px;
  }

  .title::after {
    content: "";
    position: absolute;
    top: 100%;
    left: 0;
    border: 1px solid #eeeeee;
    width: 100%;
  }
}
@media print and (max-width: 769px) {
  .title {
    position: relative;
    font-size: 24px;
  }

  .title::after {
    content: "";
    position: absolute;
    top: 100%;
    left: 0;
    border: 1px solid #eeeeee;
    width: 100%;
  }
}

@media screen and (max-width: 768px) {
  .title {
    position: relative;
    font-size: 20px;
    background-color: #fff;
  }

  .title::after {
    content: "";
    position: absolute;
    top: 100%;
    left: 0;
    border: 1px solid #eeeeee;
    width: 100%;
  }
}
</style>
