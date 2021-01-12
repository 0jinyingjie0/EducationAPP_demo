<template>
  <div class="customerServe">
    <!-- 客服页面 -->
    <div class="navTitle">{{ navTitle }}</div>
    <div class="imgAndMessage" v-for="(item,index) in messageDataList" :key="index">
      <div class="left" v-if="item.status=='left'">
        <div class="imgLeft">
          <img src="../Img/customer/kefu.png" alt="" />
        </div>
        <div class="messageLeft">
          请问有什么可以帮到您的请问有什么可以帮到您的请问有什么可以帮到您的请问有什么可以帮到您的
        </div>
      </div>

      <div class="right" v-if="item.status=='right'">
        <div class="imgRight">
          <img src="../Img/customer/kefu.png" alt="" />
        </div>
        <div class="messageRight">没事，就是随便问问</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      navTitle: "2020.12.22 10.32.00",
      messageDataList: [
        {
          status:"left"
        },
        {
          status:'right'
        }
        ], //消息信息数据集
    };
  },
};
</script>

<style lang="scss" scoped>
page {
  background-color: #fafafa !important;
}
.customerServe {
  .navTitle {
    width: 260upx;
    height: 50upx;
    line-height: 50upx;
    text-align: center;
    margin: 30upx auto;
    background: #e0e0e0;
    border-radius: 4upx;
    font-size: 24upx;
    font-family: Helvetica Neue LT Pro;
    font-weight: normal;
    color: #ffffff;
  }
  .imgAndMessage {
    width: 100%;
    margin-bottom: 36upx;
    .left {
      min-height: 100upx;
      overflow: hidden;
      .imgLeft {
        float: left;
        width: 100upx;
        height: 100upx;
        margin-left: 30upx;
        img {
          width: 100%;
        }
      }
      .messageLeft {
        float: left;
        position: relative;
        width: 460upx;
        min-height: 74upx;
        margin-left: 25upx;
        margin-top: 10upx;
        border: 4upx solid #e0e0e0;
        box-sizing: border-box;
        padding: 26upx 24upx;
        font-size: 26upx;
        font-family: PingFang SC;
        font-weight: 500;
        line-height: 37upx;
        color: #333333;
        border-radius: 10upx;
      }
      .messageLeft:before,
      .messageLeft:after {
        position: absolute;
        content: "";
        border: 20upx solid;
      }
      .messageLeft:before {
        left: -40upx;
        top: 20upx;
        border-color: transparent #e0e0e0 transparent transparent;
      }
      .messageLeft:after {
        border-color: transparent #fff transparent transparent;
        left: -36upx;
        top: 20upx;
      }
    }
    .right {
      overflow: hidden;
      min-height: 100upx;
      .imgRight {
        width: 100upx;
        height: 100upx;
        float: right;
        margin-right: 30upx;
        img {
          width: 100%;
          
        }
      }
      .messageRight {
        float: right;
        position: relative;
        width: 460upx;
        min-height: 74upx;
        margin-right: 25upx;
        margin-top: 10upx;
        border: 4upx solid #e0e0e0;
        box-sizing: border-box;
        padding: 26upx 24upx;
        font-size: 26upx;
        font-family: PingFang SC;
        font-weight: 500;
        line-height: 37upx;
        color: #333333;
         border-radius: 10upx;
      }
      .messageRight:before,
      .messageRight:after {
        position: absolute;
        content: "";
        border: 20upx solid;
      }
      .messageRight:before {
        right: -40upx;
        top: 20upx;
        border-color: transparent transparent transparent #e0e0e0;
      }
      .messageRight:after {
        border-color: transparent transparent transparent #fff;
        right: -36upx;
        top: 20upx;
      }
    }
  }
}
</style>