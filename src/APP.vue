<template>
  <screen-box :screenObj="screenObj">
    <div id="nav" class="app">
      <transition name="fade-transform" mode="out-in">
        <router-view />
      </transition>
    </div>
  </screen-box>
</template>
<script>
import ScreenBox from "./layout/Screen.vue";
export default {
  name: "large-screen",
  components: {
    ScreenBox,
  },
  data() {
    return {
      screenObj: {
        width: 1920,
        height: 1080,
      },
    };
  },
  methods: {},
};
</script>
<style lang="scss">
@import url(../src/static/css/common.scss);
.fade-transform-leave-active,
.fade-transform-enter-active {
  transition: all 0.5s;
}

.fade-transform-enter {
  opacity: 0;
}

.fade-transform-leave-to {
  opacity: 0;
}

.app {
  color: #fff;
  width: 100%;
  height: 100%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100%;
  overflow: hidden;
}
</style>
