<template>
  <view class="" style="width: 100%; overflow: hidden">
    <u-input v-model="value" :type="type" :border="border" />
    <view class="body">
      <view class="bodyContainer">
        <u-field
          v-model="userName"
          label="用户名"
          right-icon="account-fill"
          placeholder="请填写用户名"
        >
        </u-field>
        <u-field
          v-model="password"
          label="密码"
          password
          right-icon="lock-fill"
          placeholder="请填写密码"
        >
        </u-field>
        <u-button type="success" class="toLogin" @click="toLogin"
          >登录</u-button
        >
        <view class="registerContainer">
          <text>没有账号？</text
          ><text style="color: #1e19de" @click="toRegister">马上注册</text>
        </view>
      </view>
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
      loading: false,
      userName: "",
      password: "",
      value:'',
      type: 'text',
				border: true
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
      uni.navigateTo({
        url: "../login/register",
      });
    },
  },
};
</script>

<style lang="scss" scoped>


.body {
  .bodyContainer {
    width: 80%;
    height: 15rem;
    margin: 0 auto;
    margin-top: 2.5rem;
  }

  .toLogin {
    margin-top: 4rem;
  }

  .registerContainer {
    display: block;
    width: 80%;
    margin: 0 auto;
    text-align: center;
    margin-top: 1rem;
  }
}
</style>
