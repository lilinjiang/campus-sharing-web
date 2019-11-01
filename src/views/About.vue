<template>
  <div class="about">
    <van-button type="primary">一要按钮</van-button>
    <van-button type="primary">二要按钮</van-button>
  </div>
</template>

<script>
import { Button } from 'vant'

export default {
  components: {
    [Button.name]: Button
  }
}
</script>

<style lang="scss" scoped>

</style>
