<template>
  <div class="enterCourse">
    <!-- 进入课程页面 -->
    <div class="gradeBox">
      <div class="number">
        <div>
          <van-circle
            v-model="currentRate1"
            :rate="70"
            :color="gradientColor"
            layer-color="#ebedf0"
            :stroke-width="120"
            stroke-linecap="round"
            :text="text"
          />
        </div>
        <div>
          <van-circle
            v-model="currentRate2"
            :rate="0"
            :color="gradientColor"
            layer-color="#ebedf0"
            :stroke-width="120"
            stroke-linecap="round"
            text="0分"
          />
        </div>
        <div>
          <van-circle
            v-model="currentRate3"
            :rate="70"
            :color="gradientColor"
            layer-color="#ebedf0"
            :stroke-width="120"
            stroke-linecap="round"
            size="70px"
            :text="text"
          />
          <!-- <u-circle-progress active-color="#2979ff" :percent="30">
            <view class="u-progress-content">
              <view class="u-progress-dot"></view>
              <text class="u-progress-info">30分</text>
            </view>
          </u-circle-progress> -->
        </div>
      </div>
      <div class="title">
        <div>在线成绩</div>
        <div>考试成绩</div>
        <div class="last">总评成绩</div>
      </div>
    </div>
    <div class="contentBox">
      <div class="detaileBox">
        <div class="topBox">
          <div class="icon">
            <img src="../Img/enterCourse/dianbo.png" alt="" />
          </div>
          <div class="title">课程点播</div>

          <div class="right" @click="toCoursePlay">
            <img src="../Img/enterCourse/xiayibu.png" alt="" />
          </div>
          <div class="message">20/50分</div>
        </div>
        <div class="progress">
          <u-line-progress
            active-color="#2979ff"
            :percent="70"
            :show-percent="false"
          ></u-line-progress>
        </div>
        <div class="footerMessage">
          每个视频学习满10分钟即可获取相应的分数，满分50分。
        </div>
        <div class="foot"></div>
      </div>

      <div class="detaileBox">
        <div class="topBox">
          <div class="icon">
            <img src="../Img/enterCourse/zuoye.png" alt="" />
          </div>
          <div class="title">课程作业</div>

          <div class="right" @click="toCourseWork">
            <img src="../Img/enterCourse/xiayibu.png" alt="" />
          </div>
          <div class="message color">暂未完成</div>
        </div>
        <div class="progress">
          <u-line-progress
            active-color="#2979ff"
            :percent="70"
            :show-percent="false"
          ></u-line-progress>
        </div>
        <div class="footerMessage">每份作业均作答完毕即可获得完成学习。</div>
        <div class="foot"></div>
      </div>

      <div class="detaileBox">
        <div class="topBox">
          <div class="icon">
            <img src="../Img/enterCourse/taolun.png" alt="" />
          </div>
          <div class="title">课程讨论</div>

          <div class="right" @click="toCourseDis">
            <img src="../Img/enterCourse/xiayibu.png" alt="" />
          </div>
          <div class="message color"></div>
        </div>
        <div class="progress">
          <u-line-progress
            active-color="#2979ff"
            :percent="70"
            :show-percent="false"
          ></u-line-progress>
        </div>
        <div class="footerMessage">参与讨论获得分数。</div>
        <div class="foot"></div>
      </div>

      <div class="detaileBox">
        <div class="topBox">
          <div class="icon">
            <img src="../Img/enterCourse/dayi.png" alt="" />
          </div>
          <div class="title">面授答疑</div>

          <div class="right" @click="toFaceAnswer">
            <img src="../Img/enterCourse/xiayibu.png" alt="" />
          </div>
          <div class="message color"></div>
        </div>
        <div class="progress">
          <u-line-progress
            active-color="#2979ff"
            :percent="70"
            :show-percent="false"
          ></u-line-progress>
        </div>
        <div class="footerMessage">与老师进行在线互动，解答疑惑。</div>
        <div class="foot"></div>
      </div>

      <div class="detaileBox">
        <div class="topBox">
          <div class="icon">
            <img src="../Img/enterCourse/ziliao.png" alt="" />
          </div>
          <div class="title">课程资料</div>

          <div class="right" @click="toMaterial">
            <img src="../Img/enterCourse/xiayibu.png" alt="" />
          </div>
          <div class="message color">暂未查询</div>
        </div>
        <div class="progress">
          <u-line-progress
            active-color="#2979ff"
            :percent="70"
            :show-percent="false"
          ></u-line-progress>
        </div>
        <div class="footerMessage">查看资料，强化并拓展课程知识。</div>
        <div class="foot"></div>
      </div>

      <div class="detaileBox">
        <div class="topBox">
          <div class="icon">
            <img src="../Img/enterCourse/lianxi.png" alt="" />
          </div>
          <div class="title">题库练习</div>

          <div class="right" @click="toInfo">
            <img src="../Img/enterCourse/xiayibu.png" alt="" />
          </div>
          <div class="message color">非考试，仅为练习</div>
        </div>
        <div class="progress">
          <u-line-progress
            active-color="#2979ff"
            :percent="70"
            :show-percent="false"
          ></u-line-progress>
        </div>
        <div class="footerMessage">查看资料，强化并拓展课程知识。</div>
        <div class="foot"></div>
      </div>

      <div class="detaileBox">
        <div class="topBox">
          <div class="icon">
            <img src="../Img/enterCourse/kaoshi.png" alt="" />
          </div>
          <div class="title">课程考试</div>

          <div class="right" @click="toExam">
            <img src="../Img/enterCourse/xiayibu.png" alt="" />
          </div>
          <div class="message color"></div>
        </div>
        <!-- <div class="progress">
          <u-line-progress
            active-color="#2979ff"
            :percent="70"
            :show-percent="false"
          ></u-line-progress>
        </div> -->
        <div class="footerMessage margin">暂无考试</div>
        <div class="foot"></div>
      </div>
    </div>
  </div>
</template>

<script>
// import Circle from 'vant/lib/circle';
// import 'vant/lib/circle/style';
export default {
  components: {},
  data() {
    return {
      currentRate1: 0,
      currentRate2: 0,
      currentRate3: 0,
      rate: 30,
      text: "70分",
      // gradientColor: {
      //   "0%": "#91efe8",
      //   "100%": "#ccc",
      // },
      gradientColor: {
        "0%": "#91FEF8",
        "100%": "#3CBCFF",
      },
    };
  },
  mounted() {},
  methods: {
    toDetaile() {},
    toCoursePlay(){
    
      uni.navigateTo({
        url:"../courseModule/coursePlay"
      })
    },
    toCourseWork(){
       
      uni.navigateTo({
        url:"../courseModule/coursework"
      })
    },
    toCourseDis(){
      uni.navigateTo({
        url:"../courseModule/courseDiscussion"
      })
    },
    toFaceAnswer(){
      uni.navigateTo({
        url:"../component/faceAnswer/faceAnswer"
      })
    },
    toMaterial(){
       console.log("$$$");
      uni.navigateTo({
        url:"../courseModule/course_material"
      })
    },
    toInfo(){
       uni.navigateTo({
        url:"../component/info/info"
      })
    },
    toExam(){
      uni.navigateTo({
        url:"../component/courseExam/courseExam"
      })
    }
  },
};
</script>

<style lang="scss" scoped>
page {
  background-color: #fafafa !important;
}

.enterCourse {
  background-color: #fff;
  width: 710upx;
  margin: 20upx auto;
  .gradeBox {
    width: 100%;
    height: 350upx;
    // border: 1px solid pink;
    padding-top: 56upx;
    .number {
      width: 100%;
      height: 140upx;
      // background-color: #ccc;
      // margin-top: 28px;
      display: flex;
      justify-content: space-around;
      div {
        width: 140upx;
        height: 140upx;
        line-height: 140upx;
        text-align: center;
        border-radius: 50%;
        // background-color: rgb(17, 174, 236);
        position: relative;
        /deep/ .van-circle__hover {
          fill: #fff;
        }
        /deep/ .van-circle__text {
          width: 64upx;
          position: absolute;
          left: 38upx;
          top: 0px;
          font-size: 28upx;
          font-family: PingFang SC;
          font-weight: 500;
          color: #666666;
        }
      
      }
    }
    .title {
      width: 100%;
      height: 100upx;
      background: #43b4ae;
      border-radius: 10upx;
      margin-top: 54upx;
      display: flex;
      justify-content: space-around;
      div {
        width: 33.3%;
        text-align: center;
        height: 50upx;
        font-size: 28upx;
        font-family: PingFang SC;
        font-weight: 500;
        margin-top: 25upx;
        color: #ffffff;
        line-height: 50upx;
        border-right: 4upx solid rgba($color: #fff, $alpha: 0.6);
      }
      .last {
        border-right: none;
      }
    }
  }
  .contentBox {
    width: 100%;
    height: 198upx;
    margin-top: 20upx;
    // border: 1px solid pink;
    .detaileBox {
      width: 100%;
      .topBox {
        width: 100%;
        height: 34upx;
        margin-top: 40upx;
        .icon {
          width: 30upx;
          height: 34upx;
          float: left;
          margin-left: 32upx;
          img {
            width: 100%;
          }
        }
        .title {
          float: left;
          height: 34upx;
          margin-left: 14upx;
          font-size: 26upx;
          font-family: PingFang SC;
          font-weight: 500;
          color: #333333;
          line-height: 34upx;
        }
        .message {
          height: 34upx;
          float: right;
          font-size: 26upx;
          font-family: PingFang SC;
          font-weight: 500;
          color: #e92222;
          line-height: 34upx;
          margin-right: 24upx;
        }
        .color {
          color: #999 !important;
        }
        .right {
          float: right;
          width: 13upx;
          height: 24upx;
          margin-right: 30upx;
          img {
            width: 100%;
          }
        }
      }
      .progress {
        width: 100%;
        height: 10upx;
        margin-top: 30upx;
        margin-bottom: 30upx;
        // padding: 0 15px;
        box-sizing: border-box;
        position: relative;
        /deep/ .u-progress[data-v-0fa21744] {
          position: absolute;
          width: 92%;
          margin-left: 30upx;
          height: 10upx !important;
          /deep/ .u-active[data-v-0fa21744] {
            background: #44b4ae !important;
          }
        }
      }
      .footerMessage {
        margin: 0 30upx;
        font-size: 24upx;
        font-family: PingFang SC;
        font-weight: 400;
        color: #999999;
      }
      .margin {
        margin-top: 30upx !important;
      }
      .foot {
        width: 690upx;
        height: 2upx;
        margin: 22upx auto 0px;
        background-color: rgba($color: #000, $alpha: 0.1);
      }
    }
  }
}
</style>