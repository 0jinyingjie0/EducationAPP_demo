<!-- 课程资料页面 -->
<template>
	<view class="body">
		<u-navbar :is-back="true" title="课程资料" title-color="#333333" title-size="36upx" back-icon-color="#333333" :background="background">
		</u-navbar>
		<view class="container">
			<view class="un_read">
				<image class="img_icon" src="../../static/shijuan@2x.png" mode=""></image>
				<view class="name">教学大纲1</view>
				<view class="litel_name">已学习8分10秒</view>
				<u-icon class="right_icon" name="arrow-right"></u-icon>
			</view>
			<u-line class="line" color="#000000" style="opacity: 0.2"/>
			<view class="un_read">
				<image class="img_icon" src="../../static/shijuan@2x.png" mode=""></image>
				<view class="name">教学大纲2</view>
				<view class="litel_name">已学习8分10秒</view>
				<u-icon class="right_icon" name="arrow-right"></u-icon>
			</view>
			<u-line class="line" color="#000000" style="opacity: 0.2"/>
		</view>
		<!-- <u-modal v-model="show" @confirm="confirm_btn" show-cancel-button :cancel-style="cancel_style"  confirm-color="#44B4AE" width="70%" :content="content"></u-modal> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: {
					backgroundColor: '#fff',
					height: "88upx",
				},
				show: false,
				content: '你确定要清除所有缓存吗?',
				cancel_style: {
					border:'2upx',
					borderBottom:"#000000"
					// borderRight: 1px solid '#000000',					
					// opacity: '0.1'
				},
				form:{
					clear_cache: "2.18M",
					location: false,
					versions:false
				},
				location_list:[
					{
						value: '1',
						label: '江'
					},
					{
						value: '2',
						label: '湖'
					}
				],
				versions_list:[
					{
						value: '1',
						label: '江'
					},
					{
						value: '2',
						label: '湖'
					}
				],
			}
		},
		methods: {
			all_read() { //全部已读
				this.is_show_red = false
				
			},
			confirm(e) {
				console.log(e, "22");
			},
			open() {
				this.show = true;
			},
			confirm_btn(){
				console.log("确认清除")
			}
		}
	}
</script>
<style scoped lang="scss">
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
	.select_all {
		width: 464upx;
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
	.img_icon{
		display: inline-block;
		width: 24upx;
		height: 30upx;
		margin-right: 23upx;
	}
	.litel_name{
		// width: 156upx;
		margin-left: 47upx;
		margin-top: 17upx;
		height: 21upx;
		font-size: 22upx;
		font-family: PingFang SC;
		font-weight: 400;
		color: #999999;
		line-height: 23upx;
		position: relative;
	}
	.right_icon{
		position: absolute;
		top: 50upx;
		right: 30upx;
		color: #CCCCCC;
	}
</style>
