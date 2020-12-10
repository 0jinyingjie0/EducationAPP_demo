<template>
  <view class="box" style="width: 100%; overflow: hidden">
    <!-- <u-navbar
      title-color="#fff"
      back-icon-color="#ffffff"
      :is-fixed="isFixed"
      :is-back="isBack"
      :background="background"
      :back-text-style="{ color: '#fff' }"
      :title="title"
      :back-icon-name="backIconName"
      :back-text="backText"
    >
    </u-navbar> -->

    <view class="body">
      <img src="../Img/loginImg/back.png" alt="" />
      <div class="cardBox">
        <div class="card">
          <div class="cardTittle">XXX大学</div>
          <div class="userName">
            <img src="../Img/loginImg/yonghuming.png" alt="" />
            <u-input
              class=""
              v-model="userName"
              type="text"
              border
              placeholder="请输入账号/手机号"
            />
          </div>
          <div class="userPass">
            <img src="../Img/loginImg/mima.png" alt="" />
            <u-input v-model="password" type="text" border />
          </div>
          <div class="passwordBox">
            <div class="rememberPassword">
              <u-checkbox-group>
                <u-checkbox v-model="rememberPassword" active-color="#43B4AE"
                  >记住密码</u-checkbox
                >
              </u-checkbox-group>
            </div>
            <div class="forgetPassword">忘记密码？</div>
          </div>

          <u-button class="login" @click="toLogin">登录</u-button>

          <div class="registerContainer">
            新用户？
            <span class="register" @click="toRegister">立即注册</span>
          </div>
        </div>
      </div>
      <div class="segmentation">
        <img src="../Img/loginImg/zuo.png" alt="" />
        <div class="thirdPartyBoard">第三方登录</div>
        <img src="../Img/loginImg/you.png" alt="" />
      </div>
      <div class="footer">
        <div class="weixin">
          <img src="../Img/loginImg/vx.png" alt="">
        </div>
        <div class="qq">
          <img src="../Img/loginImg/QQ.png" alt="">
        </div>
      </div>
    </view>
    <u-loading mode="circle" :show="loading" color="ligntblue" size="100"></u-loading>
    <u-toast ref="uToast" />
  </view>
</template>

<script>
export default {
  data() {
    return {
      value: "",
      loading: false,
      userName: "",
      password: "",
      rememberPassword: "",
      background: {
        "background-image": "url('../Img/loginImg/back.png')",
        // "height":"54.8px"
      },
      isBack: false,
      backText: "",
      backIconName: "arrow-left",
      title: "",
      isFixed: true,
    };
  },
  methods: {
    toLogin() {
      if (this.userName == "") {
        this.$refs.uToast.show({
          title: "用户名不能为空",
          type: "warning",
        });
        return;
      }
      if (this.password == "") {
        this.$refs.uToast.show({
          title: "密码不能为空",
          type: "warning",
        });
        return;
      }
      this.loading = true;
      //   this.$request({
      //     url: this.loginURL + "/login",
      //     method: "POST",
      //     data: {
      //       loginId: this.userName,
      //       password: this.password,
      //     },
      //     success: (res) => {
      //       if (res.data.status == "REDIRECT") {
      //         var requestLogin = res.data;
      //         uni.setStorageSync("token", requestLogin.data.split("token=")[1]);
      //         this.toGetRole(requestLogin);
      //       } else {
      //         this.loading = false;
      //         this.$refs.uToast.show({
      //           title: "登录失败，请确认用户名或密码是否正确",
      //           type: "error",
      //         });
      //       }
      //     },
      //     fail: (err) => {
      //       this.loading = false;
      //       this.$refs.uToast.show({
      //         title: "网络出了小差，请稍后重试",
      //         type: "error",
      //       });
      //     },
      //   });
    },
    toGetRole(requestLogin) {
      this.$request({
        url:
          this.baseURL +
          "/user/getCurrentLoggedInUser?token=" +
          requestLogin.data.split("token=")[1],
        method: "GET",
        success: (res) => {
          this.loading = false;
          if (res != undefined && res.data.status == "SUCCESS") {
            res.data.data.platforms.forEach((item) => {
              if (item.platformCode == "CD_CDSS") {
                uni.setStorageSync("role", item.roleList[0].code);
              }
            });
            uni.setStorageSync("user", res.data.data);
            uni.switchTab({
              url: "../index/index",
            });
          } else {
            this.$refs.uToast.show({
              title: "获取角色信息失败，请稍后重试",
              type: "error",
            });
          }
        },
        fail: (err) => {
          this.loading = false;
          this.$refs.uToast.show({
            title: "网络出了小差，请稍后重试",
            type: "error",
          });
        },
      });
    },
    toRegister() {
      console.log('1231213');
      uni.navigateTo({
        url: "../login/register",
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.body {
  width: 100%;
  img {
    width: 5rem;
  }
  .cardBox {
    width: 100%;
    display: flex;
    justify-content: center;
    margin-top: -84px;
    .card {
      width: 313.2975px;
      height: 4.38rem;
      background: #ffffff;
      box-shadow: 0rem 0.1467rem 0.4933rem 0.04rem rgba(67, 180, 174, 0.09);
      border-radius: 0.1333rem;
      box-sizing: border-box;
      .cardTittle {
        margin: 39.9px 125.1px 39px 125.7px;
        width: 0.8333rem;
        height: 0.1867rem;
        font-size: 0.2rem;
        font-family: PingFang SC;
        font-weight: bold;
        color: #26c2b5;
        line-height: 0.1533rem;
      }
      .userName,
      .userPass {
        width: 240px;
        height: 36px;
        margin: 0 auto;
        .u-input {
          padding-left: 51px !important;
          .uni-input-placeholder {
            width: 92.5px;
            // height: 12px;
            height: 10.5px;
            // font-size: 12px;
            font-size: 11px;
            font-family: PingFang SC;
            font-weight: 500;
            color: #999999;
            // line-height: 12px;
            line-height: 7px;
          }
        }
      }
      .userName {
        position: relative;
        img {
          width: 15px;
          height: 17.5px;
          position: absolute;
          top: 8.5px;
          left: 15px;
        }
      }
      .userPass {
        margin-top: 23px;
        position: relative;
        img {
          width: 10px;
          height: 16px;
          position: absolute;
          top: 10px;
          left: 17.5px;
        }
      }
      .passwordBox {
        display: flex;
        justify-content: space-around;
        margin-top: 12px;
        .rememberPassword {
          /deep/ .u-checkbox__icon-wrap--checked[data-v-54acf820] {
            width: 10px !important;
            height: 10px !important;
            border-radius: 0px;
          }
          /deep/ .u-checkbox__label[data-v-54acf820] {
            // width: 39px;
            width: 48px;
            height: 10.5px;
            font-size: 10px !important;
            font-family: PingFang SC;
            font-weight: 400;
            color: #333;
            line-height: 7px;
          }
        }
        .forgetPassword {
          // width: 44.5px;
          width: 60px;
          height: 10px;
          font-size: 10px;
          font-family: PingFang SC;
          font-weight: 500;
          color: #43b4ae;
          // line-height: 7px;
        }
      }
      .login {
        margin: 32.5px auto 10.5px;
        width: 240px;
        height: 36px;
        background: #43b4ae;
        border-radius: 5px;
      }
      .registerContainer {
        // width: 79.5px;
        width: 130px;
        height: 9.5px;
        font-size: 10px;
        font-family: PingFang SC;
        font-weight: 400;
        color: #999999;
        line-height: 7px;
        margin: 0 auto;
        .register {
          color: #43b4ae;
        }
      }
    }
  }
  .segmentation {
    margin-top: 69px;
    display: flex;
    justify-content: center;
    img {
      width: 100px;
      height: 4px;
    }
    .thirdPartyBoard {
      // width: 49px;
      width: 60px;
      height: 9.5px;
      margin: 0 10px;
      font-size: 10px;
      font-family: PingFang SC;
      font-weight: 400;
      color: #999999;
      line-height: 7px;
    }
  }
  .footer {
    margin-top: 44px;
    .weixin,
    .qq {
      float: left;
      width: 36px;
      height: 36px;
      img {
        width: 100%;
      }
    }
    .weixin {
      margin-left: 118.5px;
    }
    .qq {
      margin-left: 66px;
    }
  }
}
</style>
