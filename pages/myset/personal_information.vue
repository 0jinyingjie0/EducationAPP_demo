<!-- 个人信息页面 -->
<template>
	<view class="body">
		<u-navbar class="nav" :is-back="true" title="" back-icon-color="#fff" :background="background">
			<view class="head">
				<image class="code" src="../../static/saoyisao@2x.png" mode=""></image>
				<image class="set" src="../../static/shezhi@2x.png" mode="" @click="toSetPage"></image>
			</view>
			<view class="infonamtion">
				<u-avatar class="head_photo" size="70rpx" src="/static/touxiang.png" @click="toMyMessage"></u-avatar>
				<view class="info_word">
					<view class="name">赵丽娜</view>
					<view class="school">同学，欢迎回来</view>
				</view>
				<u-icon class="right_icon" name="arrow-right"></u-icon>
			</view>
		</u-navbar>
		<view class="info_bg">
			<view class="info">
				<view class="my_find">
					我的发现
				</view>
				<view class="three_icons">
					<view class="info_icon">
						<image class="three_icon" src="../../static/chengjichaxun.png" mode="" @click="toSearchGrade"></image>
						<view class="three_word" style="margin-left: -25upx;">成绩查询</view>
					</view>
					<view class="info_icon">
						<image class="three_icon" src="../../static/daiban@2x.png" mode="" @click="toMyBacklog"></image>
						<view class="three_word" style="margin-left: -20upx;">我的待办</view>
					</view>
					<view class="info_icon">
						<image  class="three_icon" src="../Img/customer/kefu.png" mode="" @click="toServe"></image>
						<view class="three_word">找客服</view>
					</view>				
				</view>
			</view>
		</view>
		<view class="school_info">
			<view class="school_name">
				遵义职业技术学院
			</view>
			<view class="un_read">
				<image class="image_icon" src="../Img/courseImg/xiaoxi.png" mode=""></image>
				<view class="school_item" @click="toMyMsg">我的消息</view>
				<u-icon class="right_icon" name="arrow-right"></u-icon>
			</view>
			<view class="un_read">
				<image class="image_icon" src="../../static/jiaofei@2x.png" mode=""></image>
				<view class="school_item">缴费信息</view>
				<u-icon class="right_icon" name="arrow-right"></u-icon>
			</view>
			<view class="un_read">
				<image class="image_icon" src="../../static/xuanke@2x.png" mode=""></image>
				<view class="school_item" @click="toMySemester">学期选课</view>
				<u-icon class="right_icon" name="arrow-right"></u-icon>
			</view>
			<view class="un_read">
				<image class="image_icon" src="../../static/bangzhu@2x.png" mode=""></image>
				<view class="school_item">帮助与反馈</view>
				<u-icon class="right_icon" name="arrow-right"></u-icon>
			</view>
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
		height: 1000upx;
		background-color: #fafafa !important;
	}
	/deep/.uni-page-wrapper{
		// display: block;
		background-color: #ccc;  
		display: block;
		    height: 100%;
		    position: relative;
	}

	.nav {
		position: relative;
	}

	.head {
		height: 46upx;
		position: absolute;
		top: 30upx;
		right: 30upx;
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
		height: 300upx;
		width: 750upx;
		position: relative;
		position: fixed;
		z-index: 999;
	}
	
	.info {
		width: 690px;
		height: 300upx;
		background-color: #FFFFFF;
		box-shadow: 0px 2upx 16upx 0px rgba(229, 227, 227, 0.49);
		border-radius: 12upx;
		position: absolute;
		top: 110upx;
		left: 30upx;
		/* position: relative; */
		z-index: 999;
	}
	.info_icon{
		width: 130upx;
		height: 130upx;
		float: left;
		margin-left: 85upx;
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
		height: 29upx;
		font-size: 28upx;
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
	.three_icon{
		width:72upx ;
		height: 72upx;
		
	}
	.my_find{
		height: 30upx;
		font-size: 30upx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #333333;
		margin: 40upx 0upx 52upx 29upx;
	}
	.three_word{
		margin-top: 15upx;
		margin-left: -6upx;
	}
	.school_info{
		width:690upx ;
		height: 628upx;
		background-color: #FFFFFF;
		margin-top: 370upx;
		margin-left:30upx ;
		border-radius: 5upx;
		padding: 60upx 5upx 65upx 29upx;
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
	.school_item{
		display: inline-block;
		height: 50upx;
		font-size: 35upx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #333333;
		line-height: 90upx;
	}
	.image_icon{
		display: inline-block;
		width: 32upx;
		height: 40upx;
		margin-right: 23upx;
	}
	.right_icon{
		position: absolute;
		top: 50upx;
		right: 30upx;
		color: #CCCCCC;
	}
	.school_name{
		margin-bottom: 40upx;
		height: 29px;
		font-size: 30px;
		font-family: PingFang SC;
		font-weight: bold;
		color: #333333;
	}
</style>
