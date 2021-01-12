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
    width: 750upx;
  }
  .cardBox {
    width: 100%;
    display: flex;
    justify-content: center;
    margin-top: -168upx;
    .card {
      width: 626upx;
      height: 657upx;
      background: #ffffff;
      box-shadow: 0px 11upx 37upx 3upx rgba(67, 180, 174, 0.09);
      border-radius: 20upx;
      box-sizing: border-box;
      .cardTittle {
        margin: 80upx 251upx 78upx 251upx;
        width: 125upx;
        height: 28upx;
        font-size: 30upx;
        font-family: PingFang SC;
        font-weight: bold;
        color: #26c2b5;
        line-height: 23upx;
      }
      .userName,
      .userPass {
        width: 480upx;
        height: 72upx;
        margin: 0 auto;
        .u-input {
          padding-left: 102upx !important;
          .uni-input-placeholder {
            width: 210upx;
            height: 24upx;
            font-size: 24upx;
            font-family: PingFang SC;
            font-weight: 500;
            color: #999999;
            line-height: 24upx;
          }
        }
      }
      .userName {
        position: relative;
        img {
          width: 30upx;
          height: 35upx;
          position: absolute;
          top: 17upx;
          left: 30upx;
        }
      }
      .userPass {
        margin-top: 46upx;
        position: relative;
        img {
          width: 20upx;
          height: 32upx;
          position: absolute;
          top: 20upx;
          left: 35upx;
        }
      }
      .passwordBox {
        display: flex;
        justify-content: space-around;
        margin-top: 24upx;
        .rememberPassword {
          /deep/ .u-checkbox__icon-wrap--checked[data-v-54acf820] {
            width: 20upx !important;
            height: 20upx !important;
            border-radius: 0px;
          }
          /deep/ .u-checkbox__label[data-v-54acf820] {
            // width: 39px;
            width: 96upx;
            height: 24upx;
            font-size: 24upx !important;
            font-family: PingFang SC;
            font-weight: 400;
            color: #333;
            line-height: 24upx;
          }
        }
        .forgetPassword {
          // width: 44.5px;
          width: 120upx;
          height: 20upx;
          font-size: 20upx;
          font-family: PingFang SC;
          font-weight: 500;
          color: #43b4ae;
          // line-height: 7px;
        }
      }
      .login {
        margin: 65upx auto 21upx;
        width: 480upx;
        height: 72upx;
        background: #43b4ae;
        border-radius: 10upx;
      }
      .registerContainer {
        // width: 79.5px;
        width: 260upx;
        height: 19upx;
        font-size: 20upx;
        font-family: PingFang SC;
        font-weight: 400;
        color: #999999;
        line-height: 14upx;
        margin: 0 auto;
        .register {
          color: #43b4ae;
        }
      }
    }
  }
  .segmentation {
    margin-top: 138upx;
    display: flex;
    justify-content: center;
    img {
      width: 200upx;
      height: 8upx;
    }
    .thirdPartyBoard {
      // width: 49px;
      width: 120upx;
      height: 19upx;
      margin: 0 20upx;
      font-size: 20upx;
      font-family: PingFang SC;
      font-weight: 400;
      color: #999999;
      line-height: 14upx;
    }
  }
  .footer {
    margin-top: 88upx;
    .weixin,
    .qq {
      float: left;
      width: 72upx;
      height: 72upx;
      img {
        width: 100%;
      }
    }
    .weixin {
      margin-left: 237upx;
    }
    .qq {
      margin-left: 132upx;
    }
  }
}
</style>
