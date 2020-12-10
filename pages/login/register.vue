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
            <u-input v-model="password" type="text" border placeholder="请输入密码" />
          </div>
          <div class="userPass">
            <img src="../Img/loginImg/mima.png" alt="" />
            <u-input v-model="passwordAG" type="text" border placeholder="再次输入密码" />
          </div>

          <u-button class="login" @click="toLogin">登录</u-button>

          <div class="registerContainer">
            <u-checkbox-group>
              <u-checkbox v-model="rememberPassword" active-color="#43B4AE"
                >同意
                <span class="register" @click="toSearch">《隐私政策》</span></u-checkbox
              >
            </u-checkbox-group>
          </div>
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
      userName: "",
      password: "",
	  passwordAG: "",
	  rememberPassword:'',
	  loading: false
	  
    };
  },
  methods: {
	  toLogin(){},
	  toSearch(){}
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
      height: 383.5px;
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

      .login {
        margin: 39px auto 10.5px;
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
        /deep/ .u-checkbox__icon-wrap--square[data-v-54acf820] {
          width: 10px !important;
		  height: 10px !important;
		  border-radius: 0px;
        }
        /deep/ .u-checkbox__label[data-v-54acf820] {
        //   width: 73.5px;
          width: 97px;
          height: 9.5px;
          font-size: 10px;
          font-family: PingFang SC;
          font-weight: 400;
          color: #999999;
          line-height: 7px;
        }
        .register {
          color: #43b4ae;
        }
      }
    }
  }
}
</style>
