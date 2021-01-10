<template>
  <div class="detailAnswer">
    <!-- 课程讨论详细回答页面 -->
    <div class="contentBox">
      <div class="messageBox">
        <div class="imgAndTitle">
          <div class="img">
            <img src="../Img/courseImg/touxiang.png" alt="" />
          </div>

          <div class="nameAndTime">
            <div class="name">赵明明</div>
            <div class="time">2020.12.17</div>
          </div>
        </div>

        <div class="title">大家对第二章第一节怎么理解的</div>
      </div>
    </div>

    <div class="messageNo">{{ messageNo }}条回复</div>

    <div
      class="detaileAnswer"
      v-for="(item, index) in detaileAnswerList"
      :key="index"
    >
      <div class="img">
        <!-- <img :src="item.src" alt="" /> -->
        <img src="../Img/courseImg/touxiang.png" alt="" />
      </div>
      <div class="nameAndTimeAndMessage">
        <div class="name">{{ item.name }}</div>
        <div class="time">{{ item.time }}</div>
        <div class="message">{{ item.message }}</div>
      </div>
    </div>

    <div class="footer">
      <div class="search">
        <u-input v-model="footerSearch" type="text" placeholder="回答问题..." />
      </div>
      <div class="send">发送</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      messageNo: 2,
      footerSearch: "",
      detaileAnswerList: [
        {
          // src:'../Img/courseImg/touxiang.png',
          name: "赵明明",
          time: "2020.12.21",
          message: "大家对第二章第一节怎么理解的",
        },
        {
          // src:'../Img/courseImg/touxiang.png',
          name: "赵明明",
          time: "2020.12.21",
          message: "大家对第二章第一节怎么理解的",
        },
      ],
    };
  },
  created() {},
  methods: {},
};
</script>

<style scoped lang="scss">
page {
  background-color: #fafafa !important;
  
}
uni-page-wrapper {
  position: relative;
}
.detailAnswer {
  .contentBox {
    // border: 1px solid pink;
    .messageBox {
      width: 100%;
      height: 90px;
      // border-bottom: 1px solid #000;
      background-color: #fff;
      margin-bottom: 1px;
      .imgAndTitle {
        margin-top: 10px;
        height: 48.5px;
        display: flex;
        justify-content: left;
        .img {
          width: 40px;
          height: 48.5px;
          margin-left: 16px;
          img {
            width: 100%;
          }
        }
        .nameAndTime {
          margin-left: 12px;
          div {
            font-size: 13px;
            font-family: PingFang SC;
            font-weight: 500;
            color: #999999;
            line-height: 13px;
            margin-bottom: 7px;
          }
        }
      }
      .title {
        margin: 0 14px;
        font-size: 14px;
        font-family: PingFang SC;
        font-weight: 500;
        color: #999999;
        word-break: break-all;
        text-overflow: ellipsis;
        overflow: hidden;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
      }
    }
  }
  .messageNo {
    margin: 9.5px 0px 11px 15px;
    font-size: 13px;
    font-family: PingFang SC;
    font-weight: 500;
    color: #666666;
  }
  .detaileAnswer {
    width: 100%;
    height: 90px;
    background-color: #fff;
    margin-bottom: 1px;
    .img,
    .nameAndTimeAndMessage {
      float: left;
    }
    .img {
      width: 40px;
      height: 48.5px;
      margin-top: 10px;
      margin-left: 16px;
      img {
        width: 100%;
      }
    }
    .nameAndTimeAndMessage {
      margin-left: 7.5px;
      .name,
      .time,
      .message {
        font-family: PingFang SC;
        font-weight: 500;
        color: #999999;
      }
      .name {
        // margin-top: 14px;
        margin-top: 10px;
        margin-left: 3px;
        font-size: 13px;
      }
      .time {
        margin-top: 7.5px;
        margin-left: 2px;
        font-size: 13px;
      }
      .message {
        margin-top: 14.5px;
        font-size: 14px;
      }
    }
  }
  .footer {
    position: absolute;
    bottom: 10px;
    display: flex;
    justify-content: left;
    width: 100%;
    height: 65.5px;
    background-color: #e7e7e7;
    /deep/ .uni-input-wrapper {
      background-color: #fff;
    }
    /deep/ .u-input {
      padding: 0px !important;
      height: 100%;
      /deep/ .u-input__input[data-v-460c1d26] {
        height: 33px !important;
        min-height: 33px !important;
      }
      /deep/ .uni-input-wrapper {
        height: 33px;
        /deep/ .uni-input-placeholder {
          margin-left: 10px;
          font-size: 13px;
          font-family: PingFang SC;
          font-weight: 500;
          color: #b9b9b9;
        }
      }
      /deep/ .uni-input-input {
        height: 33px;
        
      }
    }
    .search {
      width: 279.5px;
      height: 33px;
      margin-top: 16px;
      margin-left: 16px;
    }
    .send {
      width: 60px;
      height: 33px;
      margin-top: 16px;
      margin-left: 5px;
      background: #43b4ae;
      line-height: 33px;
      text-align: center;
      color: #fff;
    }
  }
}
</style>