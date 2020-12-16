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
.scoreInquiry {
  /deep/ .u-scroll-box {
    height: 49.5px !important;
  }
  /deep/ .u-tab-item[data-v-3b2b1a80] {
    width: 86px !important;
    height: 12.5px !important;
    font-size: 13px !important;
    font-family: PingFang SC !important;
    font-weight: 500 !important;
    color: #333333 !important;
    line-height: 11.5px !important;
    margin-bottom: 14.5px !important;
    margin-top: 17.5px !important;
  }
  /deep/ .u-tab-bar[data-v-3b2b1a80] {
    width: 25px !important;
    height: 4.5px !important;
    border-radius: 2px !important;
    background-color: #43b4ae !important;
    // transform: translateY(0%) !important;
  }
  .hizden {
    height: 1px;
    width: 100%;
    background-color: #000;
    opacity: 0.1;
    margin-top: -5px;
  }
  .cardBox {
    width: 355px;
    height: 165px;
    background: #ffffff;
    border-radius: 5px;
    margin: 15px auto;
    box-shadow: rgba($color: #000000, $alpha: 1);
    // border: 1px solid pink;
    .titleText {
      text-align: center;
      width: 100%;
      height: 40px;
      font-size: 13px;
      font-family: PingFang SC;
      font-weight: 500;
      color: #333333;
      line-height: 40px;
    }
    .titleSolid {
      height: 1px;
      background: #000000;
      opacity: 0.1;
      border-radius: 5px;
      margin-bottom: 14px;
    }
    .contentBox {
      display: flex;
      justify-content: space-around;
      div {
        width: 33.3%;
        height: 25px;
        text-align: center;
        font-size: 14.5px;
        font-family: PingFang SC;
        font-weight: 500;
        color: #999999;
        line-height: 25px;
      }
      .left,
      .mid {
        border-right: 1px solid rgba($color: #000000, $alpha: 0.1);
      }
    }
    .paymentBox {
      display: flex;
      justify-content: space-around;
      margin-top: 9.5px;
      margin-bottom: 22.5px;
      div {
        width: 33.3%;
        height: 13.5px;
        text-align: center;
        font-size: 13.5px;
        font-family: PingFang SC;
        font-weight: 500;
        color: #e74141;
        line-height: 13.5px;
      }
    }
    .totalPoints {
      text-align: center;
      width: 100%;
      height: 40px;
      line-height: 40px;
      background: #43b4ae;
      border-radius: 5px;
      font-size: 14.5px;
      font-family: PingFang SC;
      font-weight: 500;
      color: #ffffff;
    }
  }
}
</style>