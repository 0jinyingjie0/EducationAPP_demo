<template>
	<view class="container">
		<view style="position:relative">
			<input class="uni-input" confirm-type="search" placeholder="大家都在搜:公务员" />
			<button class="btn">搜索</button>
			<!-- <button type="default" style="float: left;">通过方法跳转到about页面</button> -->
		</view>
		<view class="intro" style="margin-top:16upx">
			<p class="title">学习大作战</p>
			<p class="title1">让学习简单起来</p>
			<p class="title2">让你更优秀</p>
		</view>
		<view class="">
			<p class="word">快速通道</p>
<<<<<<< HEAD
			   <view class="little_box" @click="toMyBacklog">
				   <image src="../../static/daiban@2x.png" mode="" style="width:33.5px;height:30px;margin-left:17.5px;margin-top:10.5px;float:left"></image>
				   <p style="float:left;margin-top: 12px;margin-left:12px;font-size: 14px;">我的待办</p>
			   </view>
			   <view class="little_box1" @click="toMyStudy">
				   <image src="../../static/xuexi@2x(1).png" mode="" style="width:33.5px;height:30px;margin-left:17.5px;margin-top:10.5px;float:left"></image>
				   <p style="float:left;margin-top: 12px;margin-left:12px;font-size: 14px;">我的学习</p>
			   </view>
			   <view class="little_box" @click="toMyApply">
			   		<image src="../../static/baoming@2x.png" mode="" style="width:33.5px;height:30px;margin-left:17.5px;margin-top:10.5px;float:left"></image>
			   	    <p style="float:left;margin-top: 12px;margin-left:12px;font-size: 14px;">我要报名</p>
			   </view>
			   <view class="little_box1" @click="toMyCustom">
			   		<image src="../../static/zixun@2x.png" mode="" style="width:33.5px;height:30px;margin-left:17.5px;margin-top:10.5px;float:left"></image>
			   		<p style="float:left;margin-top: 12px;margin-left:12px;font-size: 14px;">我要咨询</p>
=======
			   <view class="little_box"  @click="toMyBacklog">
				   <image src="../../static/daiban@2x.png" mode="" style="width:63upx;height:60upx;margin-left:30upx;margin-top:20upx;float:left"></image>
				   <p style="float:left;margin-top: 38upx;margin-left:44upx;font-size: 14upx;">我的待办</p>
			   </view>
			   <view class="little_box1" @click="toMyStudy">
				   <image src="../../static/xuexi@2x(1).png" mode="" style="width:63upx;height:60upx;margin-left:30upx;margin-top:20upx;float:left"></image>
				   <p style="float:left;margin-top: 38upx;margin-left:44upx;font-size: 14upx;">我的学习</p>
			   </view>
			   <view class="little_box" @click="toMyApply">
			   		<image src="../../static/baoming@2x.png" mode="" style="width:63upx;height:60upx;margin-left:30upx;margin-top:20upx;float:left"></image>
			   	    <p style="float:left;margin-top: 38upx;margin-left:44upx;font-size: 14upx;">我要报名</p>
			   </view>
			   <view class="little_box1" @click="toMyCustom">
			   		<image src="../../static/zixun@2x.png" mode="" style="width:63upx;height:60upx;margin-left:30upx;margin-top:20upx;float:left"></image>
			   		<p style="float:left;margin-top: 38upx;margin-left:44upx;font-size: 14upx;">我要咨询</p>
>>>>>>> zhang
			   </view>
		</view>
		<view style="margin-top:280upx">
			<p class="word1">课程试听</p>
			<view class="item1">
				<image src="../../static/xuexi@2x(1).png" mode="" style="width:334upx;height:182upx;margin-top:30upx"></image>
				<p style="font-size: 26upx;font-weight: 500;color: #333333;margin-top:20upx">计算机应用基础</p>
				<p style="color: #999999;font-size:24upx;margin-top:10upx">免费试听</p>
			</view>
			<view class="item2">
				<image src="../../static/xuexi@2x(1).png" mode="" style="width:334upx;height:182upx;margin-top:30upx"></image>
				<p style="font-size: 26upx;font-weight: 500;color: #333333;margin-top:20upx">建筑制图</p>
				<p style="color: #999999;font-size:24upx;margin-top:10upx">免费试听</p>
			</view>
			<view class="item1">
				<image src="../../static/xuexi@2x(1).png" mode="" style="width:334upx;height:182upx;margin-top:30upx"></image>
				<p style="font-size: 13upx;font-weight: 500;color: #333333;margin-top:20upx">计算机应用基础</p>
				<p style="color: #999999;font-size:11.5upx;margin-top:10upx">免费试听</p>
			</view>
			<view class="item2">
				<image src="../../static/xuexi@2x(1).png" mode="" style="width:334upx;height:182upx;margin-top:15.5upx"></image>
				<p style="font-size: 13upx;font-weight: 500;color: #333333;margin-top: 20upx;">建筑制图</p>
				<p style="color: #999999;font-size:11.5upx;margin-top:10upx">免费试听</p>
			</view>
		</view>
		
		<text class="intro"></text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			}
		},
		methods: {
			toMyStudy(){
				uni.navigateTo({
					url:"../study/study"
				})
			},
			toMyApply(){
				uni.navigateTo({
					url:"../apply/index"
				})
			},
			toMyCustom(){
				uni.navigateTo({
					url:"../component/customerServe"
				})
			},
			toMyBacklog(){
				uni.navigateTo({
					url:"../myset/backlog"
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.container {
		padding: 15upx;
		font-size: 14upx;
		line-height: 24upx;
	}
	.btn{
		position:absolute;
		right:0upx;
		top: 0upx;
		width: 138upx;
        height: 70upx;
        background: #44B4AE;
        border-radius: 10upx;
        // width: 58px;
        // height: 28upx;
        line-height: 70upx;
        text-align: center;
        font-size: 30upx;
        font-weight: 500;
        color: #FFFFFF;
	}
	.intro{
		// width:100%;
		height:170upx;
		background: linear-gradient(-30deg, #69E0DA 0%, #68DFD9 100%);
		margin-top:26upx;
		margin:0 auto;
		border-radius: 10upx;
		}
	.title{
		color: #FFFFFF;
		font-size: 26upx;
		margin-left:2upx;
		/* margin-top:32upx; */
		padding:32upx;
		font-weight: bold;
	}
	.title1{
		font-size: 16.5upx;
		color: #FFFFFF;
		margin-left:32upx;
		margin-top:-16upx
	}
	.title2{
		font-size:16.5upx;
		color: #FFFFFF;
		margin-left:32upx;
		margin-top:8upx
	}
	.uni-input{
		width:98%;
		height:70upx;
		line-height:70upx;	
        background: #F0F0F0;
		font-size:25upx;
		padding-left:15upx;
		}
	.word{
		height:15upx;
		font-size: 32upx;
		font-weight: bold;
		margin-top:25.5upx
	}
	.little_box{
		width: 350upx;
		height:150upx;
		height: 100upx;
		margin-top: 30upx;
		border-radius: 10upx;
		background: #FFFFFF;
		box-shadow: 0upx 2upx 19upx 2upx rgba(230, 230, 230, 0.52);
		border-radius: 10upx;
		float: left;
	}
	.little_box1{
		width: 350upx;
		height:50upx;
		height: 100upx;
		margin-top: 30upx;
		border-radius: 10upx;
		background: #FFFFFF;
		box-shadow: 0upx 2upx 19upx 2upx rgba(230, 230, 230, 0.52);
		border-radius: 10upx;
		float: right;
	}
	.word1{
		font-size: 32upx;
		font-weight: bold;
		color: #333333;
		margin-top:30upx;
		}
		.item1{
			float: left;
		}
		.item2{
			float:right;
			/* /* margin-left:10upx */
		}
		.item3{
			float:left
		}
		.item4{
			float:right
		}
	
</style>
