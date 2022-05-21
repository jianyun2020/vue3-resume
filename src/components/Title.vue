<script lang="ts">
  // defineProps<{ titleName: string }>()
  export default {
    props: {
      titleName: String
    }
  }
</script>

<template>
  <h1 class="title">{{ titleName }}</h1>
</template>

<style scoped>
  .title {
    position: relative;
    font-size: 25px;
  }

  .title::after {
    content: '';
    position: absolute;
    top: 100%;
    left: 0;
    border: 1px solid #EEEEEE;

    width: 100%;
  }
</style>
