<!-- 我的资料页面 -->
<template>
	<view class="body">
		<u-navbar class="nav" :is-back="true" title="" back-icon-color="#fff" :background="background">
		</u-navbar>
		<view class="info_bg">
			<view class="info">
<<<<<<< HEAD
				<u-avatar class="head_photo" size="70rpx" src="/static/touxiang.png"></u-avatar>
=======
				<u-avatar class="head_photo" size="70" src="/static/touxiang.png"></u-avatar>
>>>>>>> zhang
				<view class="info_word">
					<view class="name">赵丽娜</view>
					<view class="school">遵义职业技术学院</view>
				</view>
			</view>
		</view>
		<view class="container">
			<view class="essential_information_title">基本信息</view>
<<<<<<< HEAD
			<u-form :model="form" ref="uForm"  color="#333333" label-width="100px"  align="left" style="width: 313px;" :border-bottom="false">
=======
			<u-form :model="form" ref="uForm"  color="#333333" label-width="200upx"  align="left" style="width: 626upx;" :border-bottom="false">
>>>>>>> zhang
				<u-form-item label="民族"   :border-bottom="false">
					<u-input input-align="right"  :disabled="true" v-model="form.info.nation" />
				</u-form-item>
				<u-form-item label="性别" :border-bottom="false">
					<u-input input-align="right"  :disabled="true" v-model="form.info.sex" />
				</u-form-item>
				<u-form-item label="身份证信息" :border-bottom="false">
					<u-input input-align="right"  :disabled="true" v-model="form.info.identity_card" />
				</u-form-item>
				<u-form-item label="手机号码" :border-bottom="false" >
					<u-input input-align="right"  :disabled="true" v-model="form.info.number"  />
<<<<<<< HEAD
					<u-icon name="arrow-right" color="#999999" size="28" @click="toFixPhoneNo"></u-icon>
=======
					<u-icon name="arrow-right" color="#999999" size="28"  @click="toFixPhoneNo"></u-icon>
>>>>>>> zhang
				</u-form-item>
				<u-form-item label="联系地址" :border-bottom="false" >
					<u-input input-align="right"  :disabled="true" v-model="form.info.location"   />
					<u-icon name="arrow-right" color="#999999" size="28"></u-icon>
				</u-form-item>
<<<<<<< HEAD
				<u-form-item label="账号密码修改" :border-bottom="false" >
=======
				<u-form-item label="账号密码修改" :border-bottom="false">
>>>>>>> zhang
					<u-input  input-align="right"  :disabled="true" v-model="form.info.number_password" /> 
					<!-- <u-select confirm=""  v-model="show" :list="list"></u-select> -->
					<!-- <u-icon  @click="show = true" name="arrow-right" color="#999999" size="28"></u-icon> -->
					<u-icon  name="arrow-right" color="#999999" size="28" @click="toFixPassword"></u-icon>
				</u-form-item>
				<u-form-item label="我的二维码"  >
					<u-input input-align="right"  :disabled="true" v-model="form.info.code"  />
					<u-icon name="arrow-right" color="#999999" size="28"></u-icon>
				</u-form-item>
			</u-form>
			<view class="essential_information_title">学校信息</view>
<<<<<<< HEAD
			<u-form :model="form" ref="uForm" label-width="100px" style="width: 313px;">
=======
			<u-form :model="form" ref="uForm" label-width="200upx" style="width: 626upx;">
>>>>>>> zhang
				<u-form-item label="学号" :border-bottom="false">
					<u-input input-align="right"  :disabled="true" v-model="form.school.student_number" />
				</u-form-item>
				<u-form-item label="报考学校" :border-bottom="false">
					<u-input input-align="right"  :disabled="true" v-model="form.school.targeted_school" />
				</u-form-item>
				<u-form-item label="我的专业" :border-bottom="false">
					<u-input input-align="right"  :disabled="true" v-model="form.school.specialty"  />
				</u-form-item>
				<u-form-item label="学习层次" :border-bottom="false">
					<u-input input-align="right"  :disabled="true" v-model="form.school.hierarchy"  />
				</u-form-item>
				<u-form-item label="学籍状态" :border-bottom="false">
					<u-input input-align="right"  :disabled="true" v-model="form.school.status"  />
				</u-form-item>
				<u-form-item label="入学年份" :border-bottom="false">
					<u-input input-align="right"  :disabled="true" v-model="form.school.start_year"  />
				</u-form-item>
				<u-form-item label="预计毕业时间" >
					<u-input input-align="right"  :disabled="true" v-model="form.school.end_year"  />
				</u-form-item>
			</u-form>
			<view class="essential_information_title">缴费信息</view>
			<view class="essential_information_two_title">欠费信息</view>
			<view class="line" style="color: #E92222;">
				<span class="vertical_icon">I</span>
				<span class="">第三学期学费2000元</span>
				<span class="pay_btn">去缴费</span>
			</view>
			<view class="line" style="color: #E92222;">
				<span class="vertical_icon">I</span>
				<span class="">第三学期学费2000元</span>
				<span class="pay_btn">去缴费</span>
			</view>
			<view class="essential_information_two_title">已缴费信息</view>
			<view class="line">
				<span class="vertical_icon">I</span>
				<span >第三学期学费2000元</span>
			</view>
			<view class="line">
				<span class="vertical_icon">I</span>
				<span class="">第三学期学费2000元</span>
			</view>
			<view class="essential_information_two_title">今后缴费计划</view>
			<view class="line">
				<span class="vertical_icon">I</span>
				<span class="">第三学期学费2000元</span>
			</view>
<<<<<<< HEAD
			<view class="line" style="margin-bottom: 37px;">
=======
			<view class="line" style="margin-bottom: 74upx;">
>>>>>>> zhang
				<span class="vertical_icon">I</span>
				<span class="">第三学期学费2000元</span>
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
<<<<<<< HEAD
					height: "132px",
=======
					height: "264upx",
>>>>>>> zhang
					backIconColor: '#fff'
				},
				show: false,
					list: [
						{
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
						targeted_school:'遵义职业技术学校',
						specialty:"工商企业管理（业余）",
						hierarchy:'成人教育-高升专',
						status:'在籍',
						start_year:'2019年12月',
						end_year:'2022年06月'	,
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
			toFixPhoneNo(){
				uni.navigateTo({
					url:"../../phone_number/index"
				})
			},
			toFixPassword(){
				console.log("#####");
				uni.navigateTo({
					url:"../../password/index"
				})
			}
		}
	}
</script>

<style scoped>
	.body {
<<<<<<< HEAD
		width: 375px;
=======
		width: 750upx;
>>>>>>> zhang
	}

	/* 头像 部分 */
	.info_bg {
<<<<<<< HEAD
		height: 93px;
		width: 375px;
=======
		height: 182upx;
		width: 750upx;
>>>>>>> zhang
		position: relative;
		position: fixed;
		z-index: 999;
	}

	.info {
<<<<<<< HEAD
		width: 345px;
		height: 140px;
		background-color: #FFFFFF;
		box-shadow: 0px 1px 8px 0px rgba(229, 227, 227, 0.49);
		border-radius: 6px;
		position: absolute;
		top: 33.5px;
		left: 15px;
=======
		width: 690upx;
		height: 280upx;
		background-color: #FFFFFF;
		box-shadow: 0upx 2upx 16upx 0upx rgba(229, 227, 227, 0.49);
		border-radius: 12upx;
		position: absolute;
		top: 67upx;
		left: 30upx;
>>>>>>> zhang
		/* position: relative; */
		z-index: 999;
	}

	.head_photo {
<<<<<<< HEAD
		width: 70px;
		height: 70px;
		position: absolute;
		left: 138px;
		top: -19.5px;
=======
		width: 140upx;
		height: 140upx;
		position: absolute;
		left: 276upx;
		top: -39upx;
>>>>>>> zhang
	}

	.info_word {
		position: absolute;
<<<<<<< HEAD
		top: 46px;
	}

	.name {
		width: 345px;
		height: 17px;
		line-height: 17px;
		text-align: center;
		margin: 14px 0 14.5px 0;
		color: #333333;
		font-size: 17px;
=======
		top: 92upx;
	}

	.name {
		width: 690upx;
		height: 34upx;
		line-height: 34upx;
		text-align: center;
		margin: 28upx 0 29upx 0;
		color: #333333;
		font-size: 34upx;
>>>>>>> zhang
		font-family: PingFang SC;
		font-weight: bold;
	}

	.school {
<<<<<<< HEAD
		width: 345px;
		height: 13px;
		line-height: 13px;
		text-align: center;
		color: #333333;
		font-size: 14px;
=======
		width: 690upx;
		height: 26upx;
		line-height: 26upx;
		text-align: center;
		color: #333333;
		font-size: 28upx;
>>>>>>> zhang
		font-family: PingFang SC;
		font-weight: bold;
	}

	/* 头像部分结尾 */
	.container {
<<<<<<< HEAD
		width: 375px;
		background-color: #FFFFFF;
		position: absolute;
		/* top: 189px; */
		margin-top: 180px; // 29px;
		margin-left: 30px;
		margin-right: 30px;
		margin-bottom: 37px;
	}

	.essential_information_title {
		font-size: 15px;
		font-family: PingFang SC;
		font-weight: bold;
		color: #333333;
		margin-top: 28px;
	}
	.essential_information_two_title{
		font-size: 14px;
		font-family: PingFang SC;
		font-weight: 500;
		color: #333333;
		margin-top: 40px;
	}
	.line{
		width: 375px;
		height: 13.5px;
		font-size: 14px;
		margin-top: 15px;
		
	}
	.vertical_icon{
		width: 2px;
		height: 8px;
		color: #44B4AE;
		background: #44B4AE;
		border-radius: 2px;
		margin-right: 4.5px;
	}
	.pay_btn{
		font-size: 9px;
		font-family: PingFang SC;
		font-weight: 500;
		color: #FFFFFF;
		width: 47px;
		height: 15px;
		line-height: 15px;
		background: #44B4AE;
		border-radius: 2px;
		padding: 3px 10px;
		margin-left: 120px ;
=======
		width: 750upx;
		background-color: #FFFFFF;
		position: absolute;
		/* top: 189upx; */
		margin-top: 360upx; 
		margin-left: 60upx;
		margin-right: 60upx;
		margin-bottom: 74upx;
	}

	.essential_information_title {
		font-size: 30upx;
		font-family: PingFang SC;
		font-weight: bold;
		color: #333333;
		margin-top: 56upx;
	}
	.essential_information_two_title{
		font-size: 28upx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #333333;
		margin-top: 80upx;
	}
	.line{
		width: 750upx;
		height: 27upx;
		font-size: 28upx;
		margin-top: 30upx;
		
	}
	.vertical_icon{
		width: 4upx;
		height: 16upx;
		color: #44B4AE;
		background: #44B4AE;
		border-radius: 4upx;
		margin-right: 9upx;
	}
	.pay_btn{
		font-size: 18upx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #FFFFFF;
		width: 94upx;
		height: 30upx;
		line-height: 30upx;
		background: #44B4AE;
		border-radius: 4upx;
		padding: 6upx 20upx;
		margin-left: 240upx ;
>>>>>>> zhang
	}
</style>
