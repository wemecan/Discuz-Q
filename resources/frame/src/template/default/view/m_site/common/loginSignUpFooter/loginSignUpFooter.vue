<template>
  <footer class="login-user-footer">
    <template v-if="pageName === 'login-user'||pageName === 'login-phone'||pageName==='wx-login-bd'">
      <span v-if="qcloudSms" @click="retrieveClick">忘记密码？找回</span>
      <i v-if="registerClose && qcloudSms"></i>
    </template>
    <template v-if="pageName === 'login-user'||pageName === 'login-phone'">
      <span v-if="registerClose" @click="signUpClick">注册</span>
    </template>

    <template v-else-if="pageName === 'wx-login-bd'">
      <span @click="wxSignUpBdClick">没有帐号？注册并绑定微信</span>
    </template>

    <template v-else-if="pageName === 'wx-sign-up-bd'">
      <span @click="wxLoginBdClick">已有帐号？登录并绑定微信</span>
    </template>

    <template v-else-if="pageName === 'sign-up'">
      <span @click="loginClick">已有帐号立即登录</span>
    </template>

    <template v-else-if="pageName === 'bind-phone'">
      <span @click="homeClick">{{siteMode === 'pay'?'跳过，进入支付费用':'跳过，进入首页'}}</span>
    </template>

    <template v-else-if="pageName === 'retrieve-pwd'">
      <span></span>
    </template>

    <template v-else>
      <span></span>
    </template>

  </footer>
</template>

<script>
// import '../../../../scss/m_site/common/loginSignUpFooter/loginSignUpFooter.scss'
import '../../../../defaultLess/m_site/common/common.less';
import loginSignUpFooterCon from '../../../../controllers/m_site/common/loginSignUpFooter/loginSignUpFooter'
export default {
    name: "login-sign-up-footer",
  ...loginSignUpFooterCon
}
</script>

