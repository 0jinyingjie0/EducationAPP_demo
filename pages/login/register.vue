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
            <u-input
              v-model="password"
              type="text"
              border
              placeholder="请输入密码"
            />
          </div>
          <div class="userPass">
            <img src="../Img/loginImg/mima.png" alt="" />
            <u-input
              v-model="passwordAG"
              type="text"
              border
              placeholder="再次输入密码"
            />
          </div>

          <u-button class="login" @click="toLogin">注册</u-button>
          <div class="registerContainer">
            <u-checkbox-group>
              <u-checkbox v-model="rememberPassword" active-color="#43B4AE"
                >同意
                <span class="register" @click="toSearch"
                  >《隐私政策》</span
                ></u-checkbox
              >
            </u-checkbox-group>
          </div>
        </div>
      </div>
    </view>
    <u-loading
      mode="circle"
      :show="loading"
      color="ligntblue"
      size="100"
    ></u-loading>
    <u-toast ref="uToast" />
  </view>
</template>

<script>
export default {
  data() {
    return {
      userName: "",
      password: "",
      passwordAG: "",
      rememberPassword: "",
      loading: false,
    };
  },
  methods: {
    toLogin() {},
    toSearch() {},
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
    margin-top: -169upx;
    .card {
      width: 626upx;
      height: 766upx;
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

      .login {
        margin: 78upx auto 21upx;
        width: 480upx;
        height: 72upx;
        background: #43b4ae;
        border-radius: 10px;
      }
      .registerContainer {
        // width: 79.5px;
        width: 260upx;
        height: 24upx;
        font-size: 24upx;
        font-family: PingFang SC;
        font-weight: 400;
        color: #999999;
        line-height: 24upx;
        margin: 0 auto;
        /deep/ .u-checkbox__icon-wrap--square[data-v-54acf820] {
          width: 20upx !important;
          height: 20upx !important;
          border-radius: 0px;
        }
        /deep/ .u-checkbox__label[data-v-54acf820] {
          //   width: 73.5px;
          width: 192upx;
          height: 24upx;
          font-size: 24upx;
          font-family: PingFang SC;
          font-weight: 400;
          color: #999999;
          line-height: 24upx;
        }
        .register {
          color: #43b4ae;
        }
      }
    }
  }
}
</style>
