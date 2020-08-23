<template>
  <div id="app">
    <router-view />
    <van-tabbar v-model="active" route  v-if="this.tabbarView">
      <van-tabbar-item name="home" icon="home-o" to="/home">主页</van-tabbar-item>
      <van-tabbar-item name="search" icon="search" to="/about">标签</van-tabbar-item>
      <van-tabbar-item name="friends" icon="friends-o">标签</van-tabbar-item>
      <van-tabbar-item name="setting" icon="setting-o">标签</van-tabbar-item>
    </van-tabbar>
  </div>
</template>

<script>
import { Tabbar, TabbarItem } from 'vant'
export default {
  data () {
    return {
      active: 'home',
      tabbarView: false
    }
  },
  components: {
    [Tabbar.name]: Tabbar,
    [TabbarItem.name]: TabbarItem
  },
  watch: {
    $route (to, from) {
      // 判断是否显示tabbar
      if (to.path === '/login' || to.path === '/register') {
        this.tabbarView = false
      } else {
        this.tabbarView = true
      }
    }
  }
  // beforeCreate () {
  //   window.document.body.style.backgroundColor = ''
  // },
  // beforeDestroy () {
  //   window.document.body.style.backgroundColor = ''
  // }
}
</script>
