<!-- 个人信息页面 -->
<template>
	<view class="body">
		<u-navbar class="nav" :is-back="true" title="" back-icon-color="#fff" :background="background">
			<view class="head">
				<image class="code" src="../../static/saoyisao@2x.png" mode="" ></image>
				<image class="set" src="../../static/shezhi@2x.png" mode="" @click="toSetPage"></image>
			</view>
			<view class="infonamtion">
				<u-avatar class="head_photo" size="70rpx" src="/static/touxiang.png" @click="toMyMessage"></u-avatar>
				<view class="info_word">
					<view class="name">赵丽娜</view>
					<view class="school">同学，欢迎回来</view>
				</view>
				<u-icon class="right_icon" name="arrow-right" ></u-icon>
			</view>
		</u-navbar>
		<view class="info_bg">
			<view class="info_word">
				我的发现
			</view>
			<view class="three_icon">
				
				<image src="../../static/chengjichaxun.png" mode="" @click="toSearchGrade"></image>
				<image src="../../static/daiban@2x.png" mode="" @click="toMyBacklog"></image>
				<image src="../../static/zhaokefu@2x .png" mode="" @click="toServe"></image>
			</view>
		</view>
		<view class="container">
			<div @click="toMyMsg">我的消息</div>
			<div @click="toMySemester">学期选课</div>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: {
					backgroundColor: '#44B4AE',
					height: "327upx",
					backIconColor: '#fff'
				},
				show: false,
				list: [{
						value: '1',
						label: '江'
					},
					{
						value: '2',
						label: '湖'
					}
				],
				form: {
					info: {
						nation: '汉',
						sex: '女',
						identity_card: '140566666666666666',
						number: '13666666666',
						location: '遵义职业技术学校',
						number_password: '111',
						code: '111',
					},
					school: {
						student_number: "19010104",
						targeted_school: '遵义职业技术学校',
						specialty: "工商企业管理（业余）",
						hierarchy: '成人教育-高升专',
						status: '在籍',
						start_year: '2019年12月',
						end_year: '2022年06月',
					},
					// bor_bom: false,
					// borderBottom:false,
					rules: {
						//rules中的属性名和form的属性名是一致的，同时给u-form-item的prop参数相同的属性名，prop此处参数绑定的属性名）不是变量。
						// name: [{
						// 	required: true,
						// 	message: '请输入姓名',
						// 	// 可以单个或者同时写两个触发验证方式 
						// 	trigger: ['change', 'blur'],
						// }],
						// intro: [{
						// 	min: 5,
						// 	message: '简介不能少于5个字',
						// 	trigger: 'change'
						// }]
					},
				}
			}
		},
		methods: {
			toSetPage(){
				
				uni.navigateTo({
					url:"../myset/my_set/index"
				})
			},
			toMyMessage(){
				console.log("%%%");
				uni.navigateTo({
					url:"../myset/myProfile/index"
				})
			},
			toSearchGrade(){
				uni.navigateTo({
					url:"../component/scoreInquiry"
				})
			},
			toMyMsg(){
				uni.navigateTo({
					url:"../myset/my_message/index"
				})
			},
			toMyBacklog(){
				console.log("$$$$");
				uni.navigateTo({
					url:"../myset/backlog"
				})
			},
			toServe(){
					uni.navigateTo({
					url:"../component/customerServe"
				})
			},
			toMySemester(){
				uni.navigateTo({
					url:"../myset/change_course"
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	.body {
		width: 750upx;
	}

	.nav {
		position: relative;
	}

	.head {
		height: 46upx;
		position: absolute;
		top: 100upx;
		right: 30upx;
		z-index: 999;
	}

	.code {
		width: 42upx;
		height: 42upx;
		margin-right: 42upx;
	}

	.set {
		width: 46upx;
		height: 46upx;
	}
	.infonamtion{
		position: absolute;
		top: 20upx;
		width: 750upx;
		height: 195upx;
		padding: 25upx 30upx;
	}
	/* 头像 部分 */
	.info_bg {
		height: 358upx;
		width: 750upx;
		position: relative;
		position: fixed;
		z-index: 999;
		.three_icon{
			margin-top: 100px;
			image {
				width: 80px;
				height: 80px;
			}
		}
	}
	
	.info {
		width: 750upx;
		height: 255upx;
		background-color: #FFFFFF;
		box-shadow: 0px 2upx 16upx 0px rgba(229, 227, 227, 0.49);
		border-radius: 12upx;
		position: absolute;
		top: 160upx;
		left: 30upx;
		/* position: relative; */
		z-index: 999;
	}

	.head_photo {
		width: 142upx;
		height: 142upx;
		position: absolute;
		left: -40upx;
		top: 80upx;
	}
	.info_word {
		position: absolute;
		top: 92upx;
		left: 150upx;
	}
	.name {
		height: 48upx;
		font-size: 48upx;
		line-height: 48upx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #FFFFFF;
	}

	.school {
		height: 29px;
		font-size: 28px;
		font-family: PingFang SC;
		font-weight: 400;
		color: #FFFFFF;
		margin-top: 28upx;
		opacity: 0.8;
	}
	.right_icon{
		position: absolute;
		top: 130upx;
		right: 130upx;
		color: #fff;
		font-size: 40upx
	}
	/* 头像部分结尾 */
	.container {
		width: 750upx;
		background-color: #FFFFFF;
		position: absolute;
		/* top: 189px; */
		margin-top: 360upx; // 29px;
		margin-left: 60upx;
		margin-right: 60upx;
		margin-bottom: 74upx;
	}
</style>
