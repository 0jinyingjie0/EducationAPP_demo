<template>
  <div class="coursePlay">
    <!-- 课程点播页面 -->
    <div class="demo">
      <video-player
        class="video-player vjs-custom-skin"
        ref="videoPlayer"
        :playsinline="true"
        :options="playerOptions"
        @play="onPlayerPlay($event)"
        @pause="onPlayerPause($event)"
        @ended="onPlayerEnded($event)"
        @waiting="onPlayerWaiting($event)"
        @playing="onPlayerPlaying($event)"
        @loadeddata="onPlayerLoadeddata($event)"
        @timeupdate="onPlayerTimeupdate($event)"
        @canplay="onPlayerCanplay($event)"
        @canplaythrough="onPlayerCanplaythrough($event)"
        @statechanged="playerStateChanged($event)"
        @ready="playerReadied"
      >
      </video-player>
      <!-- <div @click="onon">播放</div>
      <div @click="down">暂停</div> -->
    </div>
    <div class="centerBox">
      <div class="navBox">
        <div class="left">
          <div class="section">章节</div>
          <div class="bottomLine"></div>
        </div>
        <div class="right">播放选择</div>
        <div class="mid">完成学习倒计时363秒</div>
      </div>

      <div class="detaileBox">
        <u-collapse :accordion="false">
          <u-collapse-item title="课程案例">
            <div class="imgAndText">
              <div class="imgAndTittle">
                <div class="img">
                  <img src="../Img/courseImg/shipin.png" alt="" />
                </div>
                <div class="title">案例一：中国的财政政策</div>
              </div>
              <div class="text">需学习10分0秒，已学习5分30秒</div>
            </div>

             <div class="imgAndText">
              <div class="imgAndTittle">
                <div class="img">
                  <img src="../Img/courseImg/shipin.png" alt="" />
                </div>
                <div class="title">案例二：灯塔的故事</div>
              </div>
              <div class="text">需学习10分0秒，已学习5分30秒</div>
            </div>

             <div class="imgAndText">
              <div class="imgAndTittle">
                <div class="img">
                  <img src="../Img/courseImg/shipin.png" alt="" />
                </div>
                <div class="title">案例三：世界各国治理通货膨胀的良策</div>
              </div>
              <div class="text">需学习10分0秒，已学习5分30秒</div>
            </div>
          </u-collapse-item>

            <u-collapse-item title="习题讲解">
            <div class="imgAndText">
              <div class="imgAndTittle">
                <div class="img">
                  <img src="../Img/courseImg/shipin.png" alt="" />
                </div>
                <div class="title">习题讲解一</div>
              </div>
              <div class="text">需学习10分0秒，已学习5分30秒</div>
            </div>

             <div class="imgAndText">
              <div class="imgAndTittle">
                <div class="img">
                  <img src="../Img/courseImg/shipin.png" alt="" />
                </div>
                <div class="title">习题讲解二</div>
              </div>
              <div class="text">需学习10分0秒，已学习5分30秒</div>
            </div>

             <div class="imgAndText">
              <div class="imgAndTittle">
                <div class="img">
                  <img src="../Img/courseImg/shipin.png" alt="" />
                </div>
                <div class="title">习题讲解三</div>
              </div>
              <div class="text">需学习10分0秒，已学习5分30秒</div>
            </div>
          </u-collapse-item>
        </u-collapse>
      </div>
    </div>
  </div>
</template>

<script>
import { videoPlayer } from "vue-video-player";
import "video.js/dist/video-js.css";
export default {
  components: {
    videoPlayer,
  },
  data() {
    return {
      playerOptions: {
        playbackRates: [0.5, 1.0, 1.5, 2.0], // 可选的播放速度
        autoplay: false, // 如果为true,浏览器准备好时开始回放。
        muted: false, // 默认情况下将会消除任何音频。
        loop: false, // 是否视频一结束就重新开始。
        preload: "auto", // 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
        language: "zh-CN",
        aspectRatio: "16:9", // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
        fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
        sources: [
          {
            type: "video/mp4", // 类型
            src:
              "//sf1-hscdn-tos.pstatp.com/obj/media-fe/xgplayer_doc_video/mp4/xgplayer-demo-720p.mp4", // url地址
          },
        ],
        poster: "", // 封面地址
        notSupportedMessage: "此视频暂无法播放，请稍后再试", // 允许覆盖Video.js无法播放媒体源时显示的默认信息。
        controlBar: {
          timeDivider: true, // 当前时间和持续时间的分隔符
          durationDisplay: true, // 显示持续时间
          remainingTimeDisplay: false, // 是否显示剩余时间功能
          fullscreenToggle: true, // 是否显示全屏按钮
        },
      },
    };
  },
  mounted() {},
  methods: {
    onon() {
      this.$refs.videoPlayer.player.play(); // 播放
    },
    down() {
      this.$refs.videoPlayer.player.pause(); // 暂停
    },
    // 播放回调
    onPlayerPlay(player) {
      console.log("player play!", player);
    },

    // 暂停回调
    onPlayerPause(player) {
      console.log("player pause!", player);
    },

    // 视频播完回调
    onPlayerEnded($event) {
      // console.log(player)
    },

    // DOM元素上的readyState更改导致播放停止
    onPlayerWaiting($event) {
      // console.log(player)
    },

    // 已开始播放回调
    onPlayerPlaying($event) {
      // console.log(player)
    },

    // 当播放器在当前播放位置下载数据时触发
    onPlayerLoadeddata($event) {
      // console.log(player)
    },

    // 当前播放位置发生变化时触发。
    onPlayerTimeupdate($event) {
      // console.log(player);
    },

    //媒体的readyState为HAVE_FUTURE_DATA或更高
    onPlayerCanplay(player) {
      // console.log('player Canplay!', player)
    },

    //媒体的readyState为HAVE_ENOUGH_DATA或更高。这意味着可以在不缓冲的情况下播放整个媒体文件。
    onPlayerCanplaythrough(player) {
      // console.log('player Canplaythrough!', player)
    },

    //播放状态改变回调
    playerStateChanged(playerCurrentState) {
      console.log("player current update state", playerCurrentState);
    },

    //将侦听器绑定到组件的就绪状态。与事件监听器的不同之处在于，如果ready事件已经发生，它将立即触发该函数。。
    playerReadied(player) {
      console.log("example player 1 readied", player);
    },
  },
};
</script>

<style lang="scss" scoped>
page {
  background-color: #fafafa !important;
}
html,
body {
  width: 100%;
  height: 100%;
  margin: auto;
  overflow: hidden;
}
.coursePlay {
  .demo {
    border: 2upx solid #ccc;
  }
  /deep/ .video-js .vjs-big-play-button {
    top: 45%;
    left: 45%;
  }
  /deep/ .video-js .vjs-control-bar {
    height: 6em !important;
  }
  /deep/ .video-js .vjs-volume-panel {
    display: none !important;
  }
  /deep/ .video-js .vjs-play-progress:before {
    top: -1em;
  }
  /deep/ .video-js .vjs-playback-rate {
    display: none !important;
  }
  /deep/ .video-js .vjs-picture-in-picture-control {
    display: none !important;
  }
  /deep/ .vjs-button > .vjs-icon-placeholder:before {
    line-height: 1.2em !important;
  }
  /deep/ .vjs-button > .vjs-icon-placeholder:before {
    color: #fff !important;
  }
  /deep/ .video-js .vjs-control {
    border: none;
    background: transparent;
  }
  /deep/ .video-js .vjs-control:focus {
    border: none;
    background: transparent;
  }

  /deep/ .u-icon__icon[data-v-6e20bb40] {
    opacity: 0.6;
  }
  .centerBox {
    // background-color: pink;
    .navBox {
      width: 690upx;
      height: 82upx;
      margin: 0 auto;
      border-bottom: 2upx solid rgba($color: #000000, $alpha: 0.1);
      .left {
        height: 82upx;
        float: left;
        .section {
          width: 52upx;
          height: 26upx;
          font-size: 26upx;
          font-family: PingFang SC;
          font-weight: bold;
          color: #333333;
          margin-top: 42upx;
        }
        .bottomLine {
          width: 30upx;
          height: 6upx;
          background: #43b4ae;
          margin: 0 auto;
          margin: 10upx;
        }
      }
      .mid {
        height: 82upx;
        line-height: 82upx;
        line-break: 82upx;
        float: right;
        font-size: 24upx;
        font-family: PingFang SC;
        font-weight: 400;
        color: #999999;
        margin-right: 20upx;
      }
      .right {
        float: right;
        width: 122upx;
        height: 39upx;
        border: 2upx solid #43b4ae;
        border-radius: 10upx;
        text-align: center;
        font-size: 24upx;
        font-family: PingFang SC;
        font-weight: 400;
        color: #43b4ae;
        line-height: 38upx;
        margin-top: 22upx;
      }
    }
    .detaileBox {
      /deep/ .u-collapse-head[data-v-31fbc7f8] {
        height: 84upx;
      }
      /deep/ .u-collapse-title[data-v-31fbc7f8] {
        margin-left: 30upx;
        font-size: 26upx;
        font-family: PingFang SC;
        font-weight: 500;
        color: #333333;
        // line-height: 42px;
      }
      /deep/ .u-collapse-body {
        background-color: #fafafa;
      }
      .imgAndText {
        width: 690upx;
        height: 126upx;
        margin: 0 auto;
        padding-top: 25upx;
        box-sizing: border-box;
        border-bottom: 2upx solid rgba($color: #000000, $alpha: 0.1);
        .imgAndTittle {
          height: 34upx;
          // margin-top: 17px;
          .img {
            float: left;
            width: 30upx;
            height: 34upx;
            margin: 0 auto;
            margin-left: 30upx;
            img {
              width: 100%;
            }
          }
          .title {
            float: left;
            margin-left: 24upx;
            height: 34upx;
            line-height: 34upx;
            font-size: 32upx;
            font-family: PingFang SC;
            font-weight: 500;
            color: #333333;
          }
        }
        .text {
          margin-top: 16upx;
          margin-left: 84upx;
          font-size: 24upx;
          font-family: PingFang SC;
          font-weight: 400;
          color: #999999;
        }
      }
    }
  }
}
</style>