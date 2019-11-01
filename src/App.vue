<template>
  <div id="app">
    <router-view />
    <van-tabbar v-model="active" route >
      <van-tabbar-item name="home" icon="home-o" to="/">主页</van-tabbar-item>
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
      active: 'home'
    }
  },
  components: {
    [Tabbar.name]: Tabbar,
    [TabbarItem.name]: TabbarItem
  }
}
</script>

<style lang="scss">

</style>
