<template>
  <div class="app-container">
    <!-- 顶部header区域 -->
    <mt-header fixed title="vue 移动app"></mt-header>
    <!-- 中间的路由router-view区域 -->
    <transition>
      <router-view></router-view>
    </transition>

    <!-- 底部tabbar区域 -->
    <nav class="mui-bar mui-bar-tab">
      <router-link class="mui-tab-item" to="/home">
        <span class="mui-icon mui-icon-home"></span>
        <span class="mui-tab-label">首页</span>
      </router-link>
      <router-link class="mui-tab-item" to="/member">
        <span class="mui-icon mui-icon-contact"></span>
        <span class="mui-tab-label">会员</span>
      </router-link>
      <router-link class="mui-tab-item" to="/shoppingcart">
        <span class="mui-icon mui-icon-extra mui-icon-extra-cart">
          <span class="mui-badge" id="badge">0</span>
        </span>
        <span class="mui-tab-label">购物车</span>
      </router-link>
      <router-link class="mui-tab-item" to="/search">
        <span class="mui-icon mui-icon-search"></span>
        <span class="mui-tab-label">搜索</span>
      </router-link>
    </nav>
  </div>
</template>

<script>
import mui from "./lib/mui/js/mui.js";
export default {
  data() {
    return {};
  },
  created() {},
  mounted() {
    mui("body").on("click", "a", function() {
      document.location.href = this.href;
    });
  },
  methods: {}
};
</script>

<style lang="scss" scoped>
.mint-header {
  z-index:999;
}

* {
  touch-action: pan-y;
}
.app-container {
  padding-top: 40px;
  padding-bottom: 56px;
  overflow-x: hidden;
}

.v-enter {
  opacity: 0;
  transform: translateX(100%);
}

.v-leave-to {
  opacity: 0;
  transform: translateX(-100%);
  position: absolute;
}

.v-enter-active,
.v-leave-active {
  transition: all 0.5s ease;
}
</style>
