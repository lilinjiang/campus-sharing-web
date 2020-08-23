<template>
  <!-- 登录页面 -->
  <div class="login-container">
    <!-- 顶端内容 -->
    <div class="login-top">
      <div class="login-form">
        <van-field
        v-model="userPhone"
        clearable
        maxlength="11"
        type="number"
        placeholder="请输入手机号"
        />
        <van-field
          v-model="password"
          type="password"
          clearable
          placeholder="请输入密码"
        />
        <van-field
          v-model="sms"
          clearable
          placeholder="请输入图形验证码"
        />
        <van-button class="login-button"   type="info" round size="large">登录</van-button>
      </div>
    </div>
    <!-- 底端内容 -->
    <div class="login-bottom">
      <div class="login-menu">
        <router-link to="/foo" tag="span">忘记密码</router-link><span>|</span><router-link to="/register" tag="span">用户注册</router-link>
      </div>
      <div class="login-protocol">
        <span>登录即代表阅读并同意服务协议</span>
      </div>
    </div>
  </div>
</template>

<script>
// 导入组件 输入框
import { Field, Button } from 'vant'
export default {
  data () {
    return {
      userPhone: '',
      password: '',
      sms: ''
    }
  },
  components: {
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
.login-container{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  .login-top{
    width: 90%;
    margin-top: 50%;
    .login-form{
      .login-button{
        margin-top: 20%;
      }
    }
  }
  .login-bottom{
    position: absolute;
    bottom: 5%;
    display: flex;
    flex-direction: column;
    align-items: center;
    .login-menu{
       margin-bottom: 5px;
       display: flex;
       width: 196px;
       justify-content: space-between;
       span{
         font-size: 14px;
         font-weight: 900;
       }
       span:nth-child(2){
         color: #909399;
         font-weight: 100;
       }
    }
    .login-protocol{
      font-size: 14px;
      color: #909399;
    }
  }
}
</style>
