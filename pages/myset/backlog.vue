<!-- 我的待办页面 -->
<template>
	<view class="body">
		<u-navbar :is-back="true" title="我的待办" title-color="#ffffff" title-size="18px" back-icon-color="#fff" :background="background">
		</u-navbar>
		<u-tabs name="cate_name" active-color="#43B4AE" inactive-color="#4D4D4D" count="cate_count" :list="list" :is-scroll="false" :current="current" @change="change"></u-tabs>
		<view class="container">
			<view class="un_read">
				<view class="name">今日待办消息未读消息</view>
				<view class="litel_name">2020-11-11</view>
			</view>
			<u-line class="line" color="#000000" style="opacity: 0.2"/>
			<view class="un_read">
				<view class="name">今日待办消息未读消息</view>
				<view class="litel_name">2020-11-10</view>
			</view>
			<u-line class="line" color="#000000" style="opacity: 0.2"/>
			<view class="un_read">
				<view class="name">今日待办消息未读消息</view>
				<view class="litel_name">2020-11-10</view>
			</view>
			<u-line class="line" color="#000000" style="opacity: 0.2"/>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: {
					backgroundColor: '#44B4AE',
					height: "44px",
				},
				list: [{
					cate_name: '未读消息'
				}, {
					cate_name: '已读消息'
				}, ],
				current: 0
			}
		},
		methods: {
			change(index) {
				this.current = index;
			}
		},
	}
</script>

<style scoped>
	.body {
		width: 100%;
	}
	.container {
		background-color: #FFFFFF;
		padding: 0 30upx;
	}
	.un_read {
		width: 690upx;
		height: 142upx;
		padding: 31upx  30upx 48upx 30upx ;
		font-size: 30upx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #333333;
		position: relative;
}
	.name{
		display: inline-block;
		height: 50upx;
		font-size: 30upx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #333333;
		line-height: 50upx;
	}
	.litel_name{
		display: inline-block;
		// width: 156upx;
		margin-left: 47upx;
		margin-top: 17upx;
		height: 21upx;
		font-size: 22upx;
		font-family: PingFang SC;
		font-weight: 400;
		color: #999999;
		line-height: 23upx;
		position: absolute;
		right: 31upx;
		top: 31upx;
	}
</style>
