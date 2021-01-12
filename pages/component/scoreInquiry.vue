<template>
  <view class="scoreInquiry">
    <!-- 成绩查询页面 -->
    <u-tabs
      :list="list"
      :is-scroll="scroll"
      :current="current"
      gutter="38"
      @change="change"
    ></u-tabs>
    <div class="hizden"></div>
    <div class="cardBox" v-for="(item, index) in pointsList" :key="index">
      <div class="titleText">经济基础</div>
      <div class="titleSolid"></div>
      <div class="contentBox">
        <div class="left">在线成绩</div>
        <div class="mid">考试成绩</div>
        <div class="right">其他成绩</div>
      </div>
      <div class="paymentBox">
        <div class="onlinePayment">{{ item.onlinePayment }}分</div>
        <div class="examResults">{{ item.examResults }}分</div>
        <div class="otherGrades">{{ item.otherGrades }}分</div>
      </div>
      <div class="totalPoints">{{ item.totalPoints }}分</div>
    </div>
  </view>
</template>

<script>
export default {
  data() {
    return {
      list: [
        {
          name: "第1学期",
        },
        {
          name: "第2学期",
        },
        {
          name: "第3学期",
        },
        {
          name: "第4学期",
        },
        {
          name: "第5学期",
          count: 5,
        },
      ],
      pointsList: [
        {
          onlinePayment: "30",
          examResults: "30",
          otherGrades: "30",
          totalPoints: "90",
        },
      ],
      current: 0,
      scroll: true,
      barHeight: "6px",
      barWidth: "40px",
    };
  },
  created() {},
  methods: {
    change(index) {
      console.log("change", index);
      this.current = index;
    },
  },
};
</script>

<style lang="scss" scoped>
page {
  background-color: #fafafa !important;
}
.scoreInquiry {
  /deep/ .u-scroll-box {
    height: 99upx !important;
  }
  /deep/ .u-tab-item[data-v-3b2b1a80] {
    width: 172upx !important;
    height: 25upx !important;
    font-size: 26upx !important;
    font-family: PingFang SC !important;
    font-weight: 500 !important;
    color: #333333 !important;
    line-height: 23upx !important;
    margin-bottom: 29upx !important;
    margin-top: 35upx !important;
  }
  /deep/ .u-tab-bar[data-v-3b2b1a80] {
    width: 50upx !important;
    height: 18upx !important;
    border-radius: 8upx !important;
    background-color: #43b4ae !important;
    // transform: translateY(0%) !important;
  }
  .hizden {
    height: 2upx;
    width: 100%;
    background-color: #000;
    opacity: 0.1;
    margin-top: -10upx;
  }
  .cardBox {
    width: 710upx;
    height: 330upx;
    background: #ffffff;
    border-radius: 10upx;
    margin: 30upx auto;
    box-shadow: rgba($color: #000000, $alpha: 1);
    // border: 1px solid pink;
    .titleText {
      text-align: center;
      width: 100%;
      height: 80upx;
      font-size: 26upx;
      font-family: PingFang SC;
      font-weight: 500;
      color: #333333;
      line-height: 80upx;
    }
    .titleSolid {
      height: 2upx;
      background: #000000;
      opacity: 0.1;
      border-radius: 10upx;
      margin-bottom: 28upx;
    }
    .contentBox {
      display: flex;
      justify-content: space-around;
      div {
        width: 33.3%;
        height: 50upx;
        text-align: center;
        font-size: 29upx;
        font-family: PingFang SC;
        font-weight: 500;
        color: #999999;
        line-height: 50upx;
      }
      .left,
      .mid {
        border-right: 2upx solid rgba($color: #000000, $alpha: 0.1);
      }
    }
    .paymentBox {
      display: flex;
      justify-content: space-around;
      margin-top: 19upx;
      margin-bottom: 45upx;
      div {
        width: 33.3%;
        height: 27upx;
        text-align: center;
        font-size: 27upx;
        font-family: PingFang SC;
        font-weight: 500;
        color: #e74141;
        line-height: 27upx;
      }
    }
    .totalPoints {
      text-align: center;
      width: 100%;
      height: 80upx;
      line-height: 80upx;
      background: #43b4ae;
      border-radius: 10upx;
      font-size: 29upx;
      font-family: PingFang SC;
      font-weight: 500;
      color: #ffffff;
    }
  }
}
</style>