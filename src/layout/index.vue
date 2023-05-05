<template>
  <div class="layout-box">
    <div class="header-box">头部导航</div>
    <router-view class="content-box"></router-view>
  </div>
</template>

<script></script>

<style scoped lang="scss">
.layout-box {
  height: 100%;
  .header-box {
    width: 100%;
    height: 100px;
    background-color: gray;
  }
  .content-box {
    height: calc(100% - 100px);
  }
}
</style>
