<!-- 报名页面 -->
<template>
	<view class="body">
		<u-navbar class="nav" :is-back="true" title="" back-icon-color="#fff" :background="background">
		</u-navbar>
		<view class="container">
<<<<<<< HEAD
			<u-form :model="form" ref="uForm" color="#333333" label-width="100px" align="left" style="width: 313px;"
=======
			<u-form :model="form" ref="uForm" color="#333333" label-width="200upx" align="left" style="width: 313px;"
>>>>>>> zhang
			 :border-bottom="false">
				<u-form-item label="性名" :border-bottom="false">
					<u-input class="select_value" input-align="right" v-model="form.info.name" />
				</u-form-item>
				<u-form-item label="性别" :border-bottom="false">
					<u-select @confirm="confirm" class="select_all" v-model="sex_show" :list="sex"></u-select>
					<u-icon @click="sex_show = true" name="arrow-right" color="#999999" size="28"></u-icon>
					<!-- <u-input style="color: #44B4AE;" class="select_value" input-align="right" v-model="form.info.sex" /> -->
					<!-- <u-icon name="arrow-right" color="#999999" size="28"></u-icon> -->
				</u-form-item>
				<u-form-item label="联系方式" :border-bottom="false">
					<u-input input-align="right" v-model="form.info.number" />
<<<<<<< HEAD
					<span style="margin-left: 4.5px;">|</span>
=======
					<span style="margin-left: 9px;">|</span>
>>>>>>> zhang
				</u-form-item>
				<u-form-item label="选择学校" :border-bottom="false">
					<u-select @confirm="confirm" class="select_all" v-model="school_show" :list="school"></u-select>
					<u-icon @click="school_show = true" name="arrow-right" color="#999999" size="28"></u-icon>
				</u-form-item>
				<u-form-item label="选择科目" :border-bottom="false">
					<u-select @confirm="confirm" class="select_all" v-model="subjects_show" :list="subjects"></u-select>
					<u-icon @click="subjects_show = true" name="arrow-right" color="#999999" size="28"></u-icon>
				</u-form-item>
				<u-form-item label="选择站点" :border-bottom="false">
					<u-select @confirm="confirm" class="select_all" v-model="site_show" :list="site"></u-select>
					<u-icon @click="site_show = true" name="arrow-right" color="#999999" size="28"></u-icon>
				</u-form-item>
				<u-form-item label="是否培训" :border-bottom="false">
					<u-select @confirm="confirm" class="select_all" v-model="cultivate_show" :list="cultivate"></u-select>
					<u-icon @click="cultivate_show = true" name="arrow-right" color="#999999" size="28"></u-icon>
				</u-form-item>
				<u-form-item label="选择培训方式" :border-bottom="false">
					<u-select @confirm="confirm" class="select_all" v-model="way_show" :list="way"></u-select>
					<u-icon @click="way_show = true" name="arrow-right" color="#999999" size="28"></u-icon>
				</u-form-item>
			</u-form>
		</view>
		<view class="out_btn">退出</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: {
					backgroundColor: '#ffff',
<<<<<<< HEAD
					height: "50px",
=======
					height: "100upx",
>>>>>>> zhang
					backIconColor: '#fff'
				},
				show: false,
				sex_show: false,
				school_show: false,
				subjects_show: false,
				site_show: false,
				way_show: false,
				cultivate_show: false,
				sex: [{
						value: "1",
						label: '男'
					},
					{
						value: "2",
						label: '女'
					},
				],
				school: [{
						value: "1",
						label: '遵义职业技术学院',
					},
					{
						value: "2",
						label: '遵义职业技术学院1',
					},
				],
				subjects: [{
						value: "1",
						label: '高等数学',
					},
					{
						value: "2",
						label: '高等语文',
					},
				],
				site: [{
						value: "1",
						label: '站点培训',
					},
					{
						value: "2",
						label: '站点',
					},
				],
				way: [{
						value: "1",
						label: '面授',
					},
					{
						value: "2",
						label: '线上网课',
					},
				],
				cultivate: [{
						value: "1",
						label: '是',
					},
					{
						value: "2",
						label: '否',
					},
				],
				form: {
					info: {
						name: '张丽娜',
						number: '13666666666',
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
						name: [{
							required: true,
							message: '请输入姓名',
							// max: 5,
							// 可以单个或者同时写两个触发验证方式 
							trigger: ['change', 'blur'],
						}],
						number: [{
								required: true,
								message: '请输入手机号',
								trigger: ['change', 'blur'],
							},
							{
								// 自定义验证函数，见上说明
								validator: (rule, value, callback) => {
									// 上面有说，返回true表示校验通过，返回false表示不通过
									// this.$u.test.mobile()就是返回true或者false的
									return this.$u.test.mobile(value);
								},
								message: '手机号码不正确',
								// 触发器可以同时用blur和change
								trigger: ['change', 'blur'],
							}
						]
					},
				}
			}
		},
		methods: {
			confirm(e) {
				console.log(e, "22");
			}
		}
	}
</script>

<style scoped>
	.body {
<<<<<<< HEAD
		width: 375px;
		background-color: rgba(229, 227, 227, 0.16);
		/* margin-top: 10px; */
	}

	.container {
		width: 345px;
		background-color: #FFFFFF;
		/* height: 478px; */
		margin: -25px 15px 56px 15px;
		background: #FFFFFF;
		box-shadow: 1px 1px 1px 1px rgba(229, 227, 227, 0.49);
		border-radius: 6px;
		padding: 10px 0px 10px 10px;
=======
		/* width: 100%; */
		background-color: rgba(229, 227, 227, 0.16);
		/* margin-top: 10px; */
	}
	.container {
		/* width: 690upx; */
		background-color: #FFFFFF;
		/* height: 478px; */
		margin: -50upx 30upx 112upx 30upx;
		background: #FFFFFF;
		box-shadow: 2upx 2upx 2upx 2upx rgba(229, 227, 227, 0.49);
		border-radius: 12upx;
		padding: 20upx 0px 20upx 20upx;
>>>>>>> zhang
		color: #44B4AE;
	}

	.select_value {
		color: #44B4AE;
	}
	.select_all {
<<<<<<< HEAD
		width: 200px;
	}
	.out_btn {
		width: 345px;
		height: 49px;
		line-height: 49px;
		text-align: center;
		background: #44B4AE;
		border-radius: 6px;
		font-size: 16px;
		font-family: PingFang SC;
		font-weight: bold;
		color: #FFFFFF;
		margin-left: 15px;
=======
		width: 400upx;
	}
	.out_btn {
		/* width: 690upx; */
		height: 98upx;
		line-height: 98upx;
		text-align: center;
		background: #44B4AE;
		border-radius: 12upx;
		font-size: 32upx;
		font-family: PingFang SC;
		font-weight: bold;
		color: #FFFFFF;
		margin-right: 30px;
		margin-left: 30upx;
>>>>>>> zhang
	}
</style>
