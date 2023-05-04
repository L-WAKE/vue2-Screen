<template>
  <div class="ScreenAdapter" :style="style">
    <slot />
  </div>
</template>

<script>
import _ from "lodash";
export default {
  name: "Screen-box",
  data() {
    return {
      width: 1920,
      height: 1080,
      style: {},
    };
  },
  props: {
    screenObj: {
      type: Object,
      default: {
        width: 1920,
        height: 1080,
      },
    },
  },
  mounted() {
    this.width = this.screenObj.width || 1920;
    this.height = this.screenObj.height || 1080;
    this.style = {
      width: this.width + "px",
      height: this.height + "px",
      transform: "scale(1) translate(-50%, -50%)",
    };
    this.$nextTick(() => {
      this.setScale();
      window.onresize = _.debounce(this.setScale, 100);
    });
  },
  methods: {
    // 获取放大缩小比例
    getScale() {
      const w = window.innerWidth / this.width;
      const h = window.innerHeight / this.height;
      return w < h ? w : h;
    },
    // 设置比例
    setScale() {
      this.style.transform = "scale(" + this.getScale() + ") translate(-50%, -50%)";
    },
  },
};
</script>

<style lang="scss" scoped>
.ScreenAdapter {
  transform-origin: 0 0;
  position: absolute;
  left: 50%;
  top: 50%;
  transition: 0.3s;
}
</style>
