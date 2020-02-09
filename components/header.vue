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
         <!-- 如果用户存在则展示用户信息，用户数据来自store -->
                <el-dropdown v-if="this.$store.state.user.userInfo.token">
                    <el-row type="flex" align="middle" class="el-dropdown-link">
                        <nuxt-link to="#">
                            <img :src="$axios.defaults.baseURL+$store.state.user.userInfo.user.defaultAvatar"/>
                            {{this.$store.state.user.userInfo.user.nickname}}
                        </nuxt-link>
                        <i class="el-icon-caret-bottom el-icon--right"></i>
                    </el-row>
                    <el-dropdown-menu slot="dropdown">
                        <el-dropdown-item>
                           <nuxt-link to="#">个人中心</nuxt-link>
                        </el-dropdown-item>
                        <el-dropdown-item>
                            <div @click="exit">退出</div> 
                        </el-dropdown-item>
                    </el-dropdown-menu>
                </el-dropdown>


        <nuxt-link to="/user/login" class="account-link" v-if="!this.$store.state.user.userInfo.token">登录 / 注册</nuxt-link>
        {{this.$store.state.user.name}}
      </el-row>
    </el-row>
  </header>
</template>

<script>
export default {
  methods:{
    exit:function(){
       this.$message({
          showClose: true,
          message: '退出成功',
          type: 'success'
        });
    }
  }
};
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
      .message{
            height:36px;
            line-height:1;
            cursor:pointer;
            .el-icon-bell{
                margin-right:2px;
                font-size:18px;      
            }
        }

        .el-dropdown-link{
           margin-left:20px;

           &:hover{
               img{
                    border-color: #409eff;
               }
            }

           a{
               display:block;
           }

            img{

                width:32px;
                height:32px;
                vertical-align: middle;
                border:2px #fff solid;
                border-radius:50px;
            }
        }

        .account-link{
            font-size: 14px;
            margin-left:10px;
            color:#666;

            &:hover{
                color:#409eff;
                text-decoration: underline;
            }
        }
  }
}
</style>