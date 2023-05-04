<template>
  <div class="big-content">
    <div class="test-scorll">
      <p v-for="item in 100">这是内容{{ item }}</p>
    </div>
  </div>
</template>

<script>
//   background-color: gray;
</script>
<style scoped lang="scss">
.big-content {
  width: 100%;
  height: 100%;
  overflow-y: auto;
  background: url(../../static/image/map_bg2.jpg) center no-repeat;
  background-size: 100% 100%;
  .test-scorll {
    overflow-y: auto;
  }
}
</style>
