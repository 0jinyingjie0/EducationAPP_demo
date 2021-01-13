<!-- 选择课程页面 -->
<template>
	<view class="body">
		<u-navbar :is-back="true" title="选择课程" title-color="#ffffff" title-size="36upx" back-icon-color="#fff" :background="background">
		</u-navbar>
		<view class="tip">
			请从以下课程中选择5门课程
		</view>
		<view class="container">
			<u-checkbox-group @change="checkboxGroupChange"  :wrap=line>
				<u-checkbox  class="checkbox"  icon-size="28rpx" active-color="#44B4AE" @change="checkboxChange" shape="circle" v-model="item.checked" v-for="(item, index) in list" :key="index" :name="item.name">{{item.name}}</u-checkbox>
			</u-checkbox-group>
		</view>
		<view class="btn">
			完成
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: {
					backgroundColor: '#44B4AE',
<<<<<<< HEAD
					height: "88upx",
=======
					// height: "88upx",
>>>>>>> zhang
				},
				line:true,
				list: [{
						name: '   高等数学 （ 一 ）',
						checked: false,
						disabled: false
					},
					{
						name: '   高等数学 （ 一 ）',
						checked: false,
						disabled: false
					},
					{
						name: '   经济学基础',
						checked: false,
						disabled: false
					},
					{
						name: '   马克思主义理论基础',
						checked: false,
						disabled: false
					},
					{
						name: '   大学英语',
						checked: false,
						disabled: false
					},
					{
						name: '   计算机基础',
						checked: false,
						disabled: false
					},
					{
						name: '   毛泽东概论基础',
						checked: false,
						disabled: false
					}
				]
			}
		},
		methods: {
			// 选中某个复选框时，由checkbox时触发
					checkboxChange(e) {
						//console.log(e);
					},
					// 选中任一checkbox时，由checkbox-group触发
					checkboxGroupChange(e) {
						// console.log(e);
					},
		},
	}
</script>

<style scoped>
	.body {
<<<<<<< HEAD
		width: 750upx;
=======
		/* width: 750upx; */
>>>>>>> zhang
		background-color: rgba(229, 227, 227, 0.16);
	}

	.tip {
		/* width: 313px; */
		height: 61upx;
		font-size: 24upx;
		line-height: 61upx;
		font-family: PingFang SC;
		font-weight: 400;
		color: #999999;
		padding: 6upx 0upx 6upx 30upx;
		background-color: rgba(229, 227, 227, 0.16);
	}

	.container {
		background-color: #FFFFFF;
		padding:30upx  0 30upx 30upx;
		height: 700upx;
	}
	.checkbox{
		height: 90upx;
		font-size: 30upx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #333333;
	}
	.btn{
		background-color: rgba(229, 227, 227, 0.16);
<<<<<<< HEAD
		width: 600upx;
=======
		/* width: 600upx; */
>>>>>>> zhang
		height: 98upx;
		line-height: 98upx;
		text-align: center;
		background: #44B4AE;
		border-radius: 12upx;
		font-size: 32upx;
		font-family: PingFang SC;
		font-weight: bold;
		color: #FFFFFF;
		margin-left: 45upx;
<<<<<<< HEAD
=======
		margin-right:45upx ;
>>>>>>> zhang
		margin-top: 200upx;
	}
</style>
