<template>
	<view class="container">
		<view class="">
			<input class="uni-input" confirm-type="search" placeholder="大家都在搜:公务员" />
		</view>
		<view class="intro">
			<p class="title">学习大作战</p>
			<p class="title1">让学习简单起来</p>
			<p class="title2">让你更优秀</p>
		</view>
		<view class="">
			<p class="word">快速通道</p>
			   <view class="little_box">
				   <image src="../../static/daiban@2x.png" mode="" style="width:33.5px;height:30px;margin-left:17.5px;margin-top:10.5px;float:left"></image>
				   <p style="float:left;margin-top: 12px;margin-left:12px;font-size: 14px;">我的待办</p>
			   </view>
			   <view class="little_box1">
				   <image src="../../static/xuexi@2x(1).png" mode="" style="width:33.5px;height:30px;margin-left:17.5px;margin-top:10.5px;float:left"></image>
				   <p style="float:left;margin-top: 12px;margin-left:12px;font-size: 14px;">我的学习</p>
			   </view>
			   <view class="little_box">
			   		<image src="../../static/baoming@2x.png" mode="" style="width:33.5px;height:30px;margin-left:17.5px;margin-top:10.5px;float:left"></image>
			   	    <p style="float:left;margin-top: 12px;margin-left:12px;font-size: 14px;">我要报名</p>
			   </view>
			   <view class="little_box1">
			   		<image src="../../static/zixun@2x.png" mode="" style="width:33.5px;height:30px;margin-left:17.5px;margin-top:10.5px;float:left"></image>
			   		<p style="float:left;margin-top: 12px;margin-left:12px;font-size: 14px;">我要咨询</p>
			   </view>
		</view>
		<view style="margin-top:150px">
			<p class="word1">课程试听</p>
			<!-- <text>更多</text> -->
			<view class="item1">
				<image src="../../static/xuexi@2x(1).png" mode="" style="width:167px;height:91px;margin-top:15.5px"></image>
				<p style="font-size: 13px;font-weight: 500;color: #333333;">计算机应用基础</p>
				<p style="color: #999999;font-size:11.5px">免费试听</p>
			</view>
			<view class="item2">
				<image src="../../static/xuexi@2x(1).png" mode="" style="width:167px;height:91px;margin-top:15.5px"></image>
				<p style="font-size: 13px;font-weight: 500;color: #333333;">建筑制图</p>
				<p style="color: #999999;font-size:11.5px">免费试听</p>
			</view>
			<view style="float:left">
				<image src="../../static/xuexi@2x(1).png" mode="" style="width:167px;height:91px;margin-top:15.5px"></image>
				<p style="font-size: 13px;font-weight: 500;color: #333333;">计算机应用基础</p>
				<p style="color: #999999;font-size:11.5px">免费试听</p>
			</view>
			<view style="margin-left:11.5px">
				<image src="../../static/xuexi@2x(1).png" mode="" style="width:167px;height:91px;margin-top:15.5px;margin-left:29px"></image>
				<p style="font-size: 13px;font-weight: 500;color: #333333;margin-left:192.5px">计算机应用基础</p>
				<p style="color: #999999;font-size:11.5px;margin-left:192.5px">免费试听</p>
			</view>
		</view>
		
		<text class="intro"></text>
		<!-- <uni-link :href="href" :text="href"></uni-link> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
			}
		},
		methods: {

		}
	}
</script>

<style>
	.container {
		padding: 20px;
		font-size: 14px;
		line-height: 24px;
	}
	.intro{
		width:100%;
		height:170px;
		background: linear-gradient(-30deg, #69E0DA 0%, #68DFD9 100%);
		margin-top:16px;
		margin:0 auto;
		border-radius: 10px;
		}
	.title{
		color: #FFFFFF;
		font-size: 26px;
		margin-left:2px;
		/* margin-top:32px; */
		padding:32px;
		font-weight: bold;
	}
	.title1{
		font-size: 16.5px;
		color: #FFFFFF;
		margin-left:32px;
		margin-top:-16px
	}
	.title2{
		font-size:16.5px;
		color: #FFFFFF;
		margin-left:32px;
		margin-top:8px
	}
	.uni-input{
		width:100%;
		height:35px;
		lineheight:35px;	
        background: #F0F0F0;
		}
	.word{
		height:15px;
		font-size: 16px;
		font-weight: bold;
		margin-top:25.5px
	}
	.little_box{
		width: 167px;
		height:50px;
		/* padding: 15px 0; */
		height: 50px;
		margin-top: 20px;
		border-radius: 10px;
		background: #FFFFFF;
		box-shadow: 0px 2px 19px 2px rgba(230, 230, 230, 0.52);
		border-radius: 10px;
		float: left;
	}
	.little_box1{
		width: 167px;
		height:50px;
		/* padding: 15px 0; */
		height: 50px;
		margin-top: 20px;
		border-radius: 10px;
		background: #FFFFFF;
		box-shadow: 0px 2px 19px 2px rgba(230, 230, 230, 0.52);
		border-radius: 10px;
		float: right;
		/* margin-left:10.5px */
	}
	.word1{
		font-size: 16px;
		font-weight: bold;
		color: #333333;
		margin-top:30px;
		}
		.item1{
			float: left;
		}
		.item2{
			float:right
		}
		.item3{
			float:left
		}
		.item4{
			float:right
		}
	
</style>
