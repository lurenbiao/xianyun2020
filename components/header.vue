<template>
  <header class="header" style="jus">
    <el-row type="flex" justify="space-between" class="main">
      <div class="logo">
        <nuxt-link to="/">
          <img src="http://157.122.54.189:9093/images/logo.jpg" alt />
        </nuxt-link>
      </div>
      <el-row type="flex" class="navs">
        <nuxt-link to="/">首页</nuxt-link>
        <nuxt-link to="/post">旅游攻略</nuxt-link>
        <nuxt-link to="/hotel">酒店</nuxt-link>
        <nuxt-link to="/air">国内机票</nuxt-link>
      </el-row>

      <el-row type="flex" align="middle">
        <nuxt-link to="/user/login" class="account-link">登录 / 注册</nuxt-link>
      </el-row>
    </el-row>
  </header>
</template>

<script>
export default {};
</script>

<style lang='less'>
.header {
  height: 60px;
  line-height: 60px;
  background-color: #fff;
  border-bottom: 1px #ddd solid;
  box-shadow: 0 3px 0 #f5f5f5;
  box-sizing: border-box;

  .main {
    width: 1000px;
    margin: 0 auto;

    .logo {
      width: 156px;
      padding-top: 8px;
      img {
        display: block;
        width: 100%;
      }
    }
    .navs {
      margin: 0px 20px;
      flex: 1;
      a {
        display: block;
        padding: 0px 20px;
        height: 60px;
        box-sizing: border-box;

        &:hover,
        &:focus,
        &:active {
          border-bottom: 5px #409eff solid;
          color: #409eff;
        }
      }

      /deep/ .nuxt-link-exact-active {
        background: #409eff;
        color: #fff !important;
      }
    }
  }
}
</style>