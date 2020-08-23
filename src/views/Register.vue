<template>
  <div class="register-container">
    <van-nav-bar
      left-arrow
      @click-left="onClickLeft"
    />
    <div class="register-body">
      <div class="register-body-top">
        <h1>用手机号码注册</h1>
        <span>注册即代表阅读并同意<router-link to="/dddd">服务协议</router-link>和<router-link to="/dddd">隐私政策</router-link></span>
      </div>
        <div class="register-form">
          <van-field
          v-model="userPhone"
          clearable
          maxlength="11"
          type="number"
          placeholder="请输入手机号"
          />
          <van-button class="login-button"   type="info" round size="large">下一步</van-button>
        </div>
    </div>
  </div>
</template>

<script>
import { NavBar, Field, Button } from 'vant'
export default {
  data () {
    return {
      userPhone: ''
    }
  },
  methods: {
    onClickLeft () {
      this.$router.go(-1)
    }
  },
  components: {
    [NavBar.name]: NavBar,
    [Field.name]: Field,
    [Button.name]: Button
  },
  beforeCreate () {
    // 每当该组件创建的时候将body的颜色改变
    window.document.body.style.backgroundColor = '#FFFFFF'
  },
  beforeDestroy () {
    // 每当该组件销毁的时候将body的颜色改变
    window.document.body.style.backgroundColor = '#FFFFFF'
  }
}
</script>

<style lang="scss" scoped>
[class*=van-hairline]::after {
    border: none
}
.van-nav-bar .van-icon {
    color: #909399;
    font-weight: 400;
    font-size: 22px;
}
.register-container{
  .van-nav-bar{
    margin-top: 10px;
  }
  .register-body{
    display: flex;
    flex-direction: column;
    align-items:center;
    .register-body-top{
      width: 80%;
      h1{
        margin: 10px 0px 8px 0px;
      }
      span{
        font-size: 13px;
        a{
          color: #409EFF;
        }
      }
    }
    .register-form{
      width: 88%;
      .login-button{
        margin-top: 20px;
      }
    }
  }
}

</style>
