<!-- 患者详情和患者添加页 -->
<template>
	<view class="">
		<u-navbar title-color="#fff" back-icon-color="#ffffff" :is-fixed="isFixed" :is-back="isBack" :background="background"
		 :back-text-style="{color: '#fff'}" :title="title" :back-icon-name="backIconName" :back-text="backText" :custom-back="toBack">

			<view class="navbar-right" slot="right">
				<view class="saveItem" @click="saveItem()">
					注册
				</view>
			</view>
		</u-navbar>
		<view class="patientDetail">
			<view class="patientInfo">
				<u-field v-model="registerObj.loginId" label="用户名" required></u-field>
				<u-field v-model="registerObj.password" label="密码" required></u-field>
				<view class="input_span" v-show="passWordFlag">
					<span id="one" :style="{background:navBac1}"></span>
					<span id="two" :style="{background:navBac2}"></span>
					<span id="three" :style="{background:navBac3}"></span>
				</view>
				<br v-show="passWordFlag">
				<u-field v-model="registerObj.passwordAgain" label="确认密码" required></u-field>
				<u-field v-model="registerObj.realName" label="真实姓名" required></u-field>

				<u-field v-model="registerObj.gender" label="性别" required disabled @click="showGenderSelect"></u-field>
				<u-select v-model="flagGender" mode="single-column" :list="listGender" @confirm="confirmGender"></u-select>

				<u-field v-model="registerObj.userType" label="角色" required disabled @click="showRoleSelect"></u-field>
				<u-select v-model="flagRole" mode="single-column" :list="listRole" @confirm="confirmRole"></u-select>


				<u-field v-model="registerObj.department" label="所属部门" v-show="doctorFlag" required></u-field>
				<u-field v-model="registerObj.position" label="职位" v-show="doctorFlag" required></u-field>

				<u-field v-model="registerObj.clinicId" label="门诊号" v-show="patientFlag" required></u-field>
				<u-field v-model="registerObj.patientNo" label="住院号" v-show="patientFlag" required></u-field>


				<u-field v-model="registerObj.mobile" label="手机号" required></u-field>
				<u-field v-model="registerObj.email" label="邮箱"></u-field>

			</view>
			<u-loading mode="circle" :show="loading" color="ligntblue" size="100"></u-loading>
			<u-toast ref="uToast" />
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				navBac1: "",
				navBac2: "",
				navBac3: "",
				doctorFlag: false,
				patientFlag: false,
				passWordFlag: false,
				msgText: "",
				background: {
					"background-image": "linear-gradient(45deg, rgb(28, 187, 180), rgb(141, 198, 63))"
				},
				isBack: true,
				backText: "",
				backIconName: "arrow-left",
				title: "用户注册页",
				isFixed: true,
				registerObj: {
					loginId: "",
					password: "",
					passwordAgain: "",
					realName: "",
					gender: "",
					department: "",
					position: "",
					mobile: "",
					email: "",
					userType: "",
					clinicId: "",
					patientNo: ""
				},
				loading: false,
				flagGender: false,
				flagRole: false,
				listGender: [{
						value: "1",
						label: "男"
					},
					{
						value: "2",
						label: "女"
					}
				],
				listRole: [{
						value: "patient",
						label: "病人"
					},
					{
						value: "doctor",
						label: "医生"
					},
					{
						value: "researchers",
						label: "科研人员"
					}
				],
			}
		},
		watch: {
			"registerObj.userType": function(newVal) {
				if (newVal == "病人") {
					this.patientFlag = true;
					this.doctorFlag = false;
				} else {
					this.patientFlag = false;
					this.doctorFlag = true;
				}
			},
			"registerObj.password": function(newname, oldname) {
				if (newname.length > 0) {
					this.passWordFlag = true;
				} else {
					this.passWordFlag = false;
				}
				this.msgText = this.checkStrong(newname);

			},
			"msgText": function(newVal) {
				if (newVal > 1 || newVal == 1) {
					this.navBac1 = "red";
				} else {
					this.navBac1 = "#eee";
				}
				if (newVal > 2 || newVal == 2) {
					this.navBac2 = "orange";
				} else {
					this.navBac2 = "#eee";
				}
				if (newVal == 4) {
					this.navBac3 = "#00D1B2";
				} else {
					this.navBac3 = "#eee";
				}
			}
		},
		methods: {
			showGenderSelect() {
				this.flagGender = true
			},
			showRoleSelect() {
				this.flagRole = true
			},
			confirmGender(e) {
				this.flagGender = false;
				this.registerObj.gender = e[0].label;
			},
			confirmRole(e) {
				this.flagRole = false;
				this.registerObj.userType = e[0].label;
			},
			checkStrong(sValue) {
				var modes = 0;
				// 正则表达式验证符合要求的
				if (sValue.length < 1) return modes;
				if (/\d/.test(sValue)) modes++; // 数字
				if (/[a-z]/.test(sValue)) modes++; // 小写
				if (/[A-Z]/.test(sValue)) modes++; // 大写
				if (/\W/.test(sValue)) modes++; // 特殊字符

				// 逻辑处理
				switch (modes) {
					case 1:
						return 1;
					case 2:
						return 2;
					case 3:
					case 4:
						return sValue.length < 4 ? 3 : 4;
				}
				return modes;
			},
			saveItem() {
				if (this.registerObj.loginId == "") {
					this.$refs.uToast.show({
						title: "用户名不能为空",
						type: "warning"
					})
					return
				}
				if (this.registerObj.password == "") {
					this.$refs.uToast.show({
						title: "密码不能为空",
						type: "warning"
					})
					return
				} else if (this.registerObj.password.length < 6) {
					this.$refs.uToast.show({
						title: "密码输入长度不能小于6位",
						type: "warning"
					})
					return
				}
				if (this.registerObj.passwordAgain == "") {
					this.$refs.uToast.show({
						title: "确认密码不能为空",
						type: "warning"
					})
					return
				}
				if (this.registerObj.realName == "") {
					this.$refs.uToast.show({
						title: "真实姓名不能为空",
						type: "warning"
					})
					return
				}
				if (this.registerObj.gender == "") {
					this.$refs.uToast.show({
						title: "性别不能为空",
						type: "warning"
					})
					return
				}
				if (this.registerObj.userType == "") {
					this.$refs.uToast.show({
						title: "角色不能为空",
						type: "warning"
					})
					return
				}
				if (this.registerObj.userType == "病人") {
					if (this.registerObj.clinicId == "" && this.registerObj.patientNo == "") {
						this.$refs.uToast.show({
							title: "门诊号和住院号至少填写一项",
							type: "warning"
						})
						return
					}
				} else {
					if (this.registerObj.department == "") {
						this.$refs.uToast.show({
							title: "所属部门不能为空",
							type: "warning"
						})
						return
					}
					if (this.registerObj.position == "") {
						this.$refs.uToast.show({
							title: "职位不能为空",
							type: "warning"
						})
						return
					}
				}
				if (this.registerObj.mobile != "") {
					var pattern = /^((0\d{2,3}-\d{7,8})|(1[3576849]\d{9}))$/;
					if (!pattern.test(this.registerObj.mobile)) {
						this.$refs.uToast.show({
							title: "请输入正确的手机号码",
							type: "error"
						})
						return
					}
				}else {
					this.$refs.uToast.show({
						title: "手机号码不能为空",
						type: "warning"
					})
					return
				}
				if (this.registerObj.email != "") {
					var pattern = /^[a-zA-Z0-9]+@[a-zA-Z0-9]+\.[a-zA-Z0-9]+$/;
					if (!pattern.test(this.registerObj.email)) {
						this.$refs.uToast.show({
							title: "请输入正确的邮箱",
							type: "error"
						})
						return
					}
				}
				if (this.registerObj.password !== this.registerObj.passwordAgain) {
					this.$refs.uToast.show({
						title: "两次输入的密码不一致",
						type: "error"
					});
					return;
				}
				if (this.registerObj.userType == "病人") {
					this.registerObj.userType = "PATIENT"
				} else if (this.registerObj.userType == "医生") {
					this.registerObj.userType = "DOCTOR"
				} else {
					this.registerObj.userType = "RESEARCHERS"
				}
				this.loading = true;
				this.$request({
					url: this.loginURL + "/register",
					method: "POST",
					data: this.registerObj,
					success: (res) => {
						this.loading = false;
						if (res.data.status == "SUCCESS") {
							var content = "";
							if (this.registerObj.userType == "PATIENT") {
								content = "注册成功";
							} else {
								content = "注册成功，请联系管理员授权";
							}
							this.$refs.uToast.show({
								title: content,
								type: "success"
							})
							uni.navigateTo({
								url: "/pages/login/login"
							})
						} else {
							this.resetData()
							this.$refs.uToast.show({
								title: "注册失败，请稍后重试",
								type: "error"
							})
						}
					},
					fail: (err) => {
						this.resetData()
						this.loading = false;
						this.$refs.uToast.show({
							title: "网络出了小差，请稍后重试",
							type: "error"
						})
					}
				});
			},
			toBack() {
				uni.navigateBack({
					url: "/pages/login/login"
				})
			},
			resetData() {
				if (this.registerObj.userType == "PATIENT") {
					this.registerObj.userType = "病人"
				} else if (this.registerObj.userType == "DOCTOR") {
					this.registerObj.userType = "医生"
				} else {
					this.registerObj.userType = "科研人员"
				}
			}
		},
		onLoad(options) {

		}
	}
</script>

<style lang="scss" scoped>
	.patientDetail {
		width: 100%;

		/deep/ .u-label {
			color: darkseagreen;
		}

		/deep/ .fild-body .u-flex {
			text-align: center !important;
		}
	}

	.saveItem {
		width: 3rem;
		display: block;
		height: 2rem;
		line-height: 2rem;
		color: darkblue;
		font-size: .8rem;
	}

	.input_span {
		float: left;
		height: 20px;
	}

	.input_span span {
		display: inline-block;
		width: 40px;
		height: 10px;
		background: #eee;
		line-height: 20px;
	}

	#one {
		border-top-left-radius: 5px;
		border-bottom-left-radius: 5px;
		border-right: 0px solid;
		margin-left: 20px;
		margin-right: 3px;
	}

	#two {
		border-left: 0px solid;
		border-right: 0px solid;
		margin-left: -5px;
		margin-right: 3px;
	}

	#three {
		border-top-right-radius: 5px;
		border-bottom-right-radius: 5px;
		border-left: 0px solid;
		margin-left: -5px;
	}
</style>
