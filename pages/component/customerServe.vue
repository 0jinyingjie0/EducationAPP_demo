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
    width: 130px;
    height: 25px;
    line-height: 25px;
    text-align: center;
    margin: 15px auto;
    background: #e0e0e0;
    border-radius: 2px;
    font-size: 12px;
    font-family: Helvetica Neue LT Pro;
    font-weight: normal;
    color: #ffffff;
  }
  .imgAndMessage {
    width: 100%;
    margin-bottom: 18px;
    .left {
      min-height: 50px;
      overflow: hidden;
      .imgLeft {
        float: left;
        width: 50px;
        height: 50px;
        margin-left: 15px;
        img {
          width: 100%;
        }
      }
      .messageLeft {
        float: left;
        position: relative;
        width: 230px;
        min-height: 37px;
        margin-left: 12.5px;
        margin-top: 5px;
        border: 2px solid #e0e0e0;
        box-sizing: border-box;
        padding: 13px 12px;
        font-size: 13px;
        font-family: PingFang SC;
        font-weight: 500;
        line-height: 18.5px;
        color: #333333;
        border-radius: 5px;
      }
      .messageLeft:before,
      .messageLeft:after {
        position: absolute;
        content: "";
        border: 10px solid;
      }
      .messageLeft:before {
        left: -20px;
        top: 10px;
        border-color: transparent #e0e0e0 transparent transparent;
      }
      .messageLeft:after {
        border-color: transparent #fff transparent transparent;
        left: -18px;
        top: 10px;
      }
    }
    .right {
      overflow: hidden;
      min-height: 50px;
      .imgRight {
        width: 50px;
        height: 50px;
        float: right;
        margin-right: 15px;
        img {
          width: 100%;
          
        }
      }
      .messageRight {
        float: right;
        position: relative;
        width: 230px;
        min-height: 37px;
        margin-right: 12.5px;
        margin-top: 5px;
        border: 2px solid #e0e0e0;
        box-sizing: border-box;
        padding: 13px 12px;
        font-size: 13px;
        font-family: PingFang SC;
        font-weight: 500;
        line-height: 18.5px;
        color: #333333;
         border-radius: 5px;
      }
      .messageRight:before,
      .messageRight:after {
        position: absolute;
        content: "";
        border: 10px solid;
      }
      .messageRight:before {
        right: -20px;
        top: 10px;
        border-color: transparent transparent transparent #e0e0e0;
      }
      .messageRight:after {
        border-color: transparent transparent transparent #fff;
        right: -18px;
        top: 10px;
      }
    }
  }
}
</style>