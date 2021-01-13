<template>
<!-- 答题页面 -->
  <view class style="padding: 20upx;">
    <view class style="width:100%;height: 30upx;">
      <view style="margin-left:15upx;float: left;height:30upx;margin-top: 10up">作业1</view>
      <view class style="float:right;padding-right:20upx;height: 30upx;">1/100</view>
    </view>
    <view class style="margin-left:15upx;margin-top:15upx">(单选题，1.0分)经济学的基础是什么</view>
    <view class="item" style>
      <view class="info">A</view>
      <view class="info_word">经济学的基础是</view>
    </view>
	 <view class="item" style>
      <view class="info">B</view>
      <view class="info_word">经济学的基础是</view>
    </view>
	 <view class="item" style>
      <view class="info">C</view>
      <view class="info_word">经济学的基础是</view>
    </view>
	 <view class="item" style>
      <view class="info">D</view>
      <view class="info_word">经济学的基础是</view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {}
};
</script>

<style>
.item {
  height: 80upx;
  /* margin-top: 10upx; */
}
.info {
  display:inline-block;
  width: 40upx;
  height: 40upx;
  background-color: #ccc;
  border-radius: 50upx;
  margin-left: 15upx;
  margin-top: 15upx;
  text-align: center;
  line-height: 40upx;
  font-size: 20upx;
}
.info_word {
  display:inline-block;
  line-height: 40upx;
  margin-top: 15upx;
  margin-left: 16upx;
}
</style>
