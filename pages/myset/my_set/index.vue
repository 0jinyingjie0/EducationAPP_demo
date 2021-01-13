<!-- 我的设置页面 -->
<template>
	<view class="body">
<<<<<<< HEAD
		<u-navbar :is-back="true" title="我的设置" title-color="#ffffff" title-size="18px" back-icon-color="#fff" :background="background">
			<!-- <view class="navbar-right" slot="right" @click="all_read"> 全标已读</view> -->
		</u-navbar>
		<view class="container">
			<u-form :model="form" ref="uForm" label-width="100px"  >
=======
		<u-navbar :is-back="true" title="我的设置" title-color="#ffffff" title-size="18upx" back-icon-color="#fff" :background="background">
			<!-- <view class="navbar-right" slot="right" @click="all_read"> 全标已读</view> -->
		</u-navbar>
		<view class="container">
			<u-form :model="form" ref="uForm" label-width="660upx"  >
>>>>>>> zhang
				<u-form-item label="选择省份" :border-bottom="false">					
					<u-select @confirm="confirm" class="select_all" v-model="form.location" :list="location_list"></u-select>
					<u-icon @click="form.location = true" name="arrow-right" color="#999999" size="28"></u-icon>
				</u-form-item>
				<u-line class="line" color="#000000" style="opacity: 0.2"/>
				<u-form-item label="清理缓存" :border-bottom="false">
<<<<<<< HEAD
					<u-input input-align="right" @click="open"  v-model="form.clear_cache"  />
=======
					<u-input input-align="left" style="margin-left:-60upx" @click="open"  v-model="form.clear_cache"  />
>>>>>>> zhang
				</u-form-item>
				<u-line class="line" color="#000000" style="opacity: 0.2"/>
				<u-form-item label="关于" :border-bottom="false">
					<u-select @confirm="confirm" class="select_all" v-model="form.versions" :list="versions_list"></u-select>
					<u-icon @click="form.versions = true" name="arrow-right" color="#999999" size="28"></u-icon>
				</u-form-item>
				<u-line class="line" color="#000000" style="opacity: 0.2"/>
			</u-form>
		</view>
		<u-modal v-model="show" @confirm="confirm_btn" show-cancel-button :cancel-style="cancel_style"  confirm-color="#44B4AE" width="70%" :content="content"></u-modal>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: {
					backgroundColor: '#44B4AE',
<<<<<<< HEAD
					height: "44px",
=======
					// height: "44upx",
>>>>>>> zhang
				},
				show: false,
				content: '你确定要清除所有缓存吗?',
				cancel_style: {
<<<<<<< HEAD
					border:'1px',
					borderBottom:"#000000"
					// borderRight: 1px solid '#000000',					
=======
					border:'1upx',
					borderBottom:"#000000"
					// borderRight: 1upx solid '#000000',					
>>>>>>> zhang
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

<style scoped>
	.body {
<<<<<<< HEAD
		width: 375px;
	}

	.navbar-right {
		margin-right: 15px;
		font-size: 15px;
=======
		/* width: 375upx; */
	}

	.navbar-right {
		margin-right: 15upx;
		font-size: 15upx;
>>>>>>> zhang
		font-family: PingFang SC;
		font-weight: 500;
		color: #FFFFFF;
		opacity: 0.9;
	}
	.container {
		background-color: #FFFFFF;
<<<<<<< HEAD
		padding: 0 15px;
	}
	.un_read {
		width: 345px;
		height: 60px;
		padding: 23px 0;
		font-size: 15px;
=======
		padding: 0 15upx;
	}
	.un_read {
		/* width: 345upx; */
		height: 60upx;
		padding: 23upx 0;
		font-size: 15upx;
>>>>>>> zhang
		font-family: PingFang SC;
		font-weight: 500;
		color: #333333;
		position: relative;
	}
	.select_all {
<<<<<<< HEAD
		width: 232px;
=======
		/* width: 232upx; */
>>>>>>> zhang
	}
</style>
