<!-- 我的消息页面 -->
<template>
	<view class="body">
<<<<<<< HEAD
		<u-navbar :is-back="true" title="我的消息" title-color="#ffffff" title-size="18px" back-icon-color="#fff" :background="background">
=======
		<u-navbar :is-back="true" title="我的消息" title-color="#ffffff" title-size="18upx" back-icon-color="#fff" :background="background">
>>>>>>> zhang
			<view class="navbar-right" slot="right" @click="all_read"> 全标已读</view>
		</u-navbar>
		<view class="container">
			<view class="un_read">
				<span v-if="is_show_red" class="small_red"></span>
				<span>{{unread}}</span>
				<span class="time">{{unread_time}}</span>
				<u-line class="line" color="#000000" style="opacity: 0.2"/>
			</view>
			<view class=" un_read read">
				<span v-if="is_show_red" class="small_red"></span>
				<span>{{unread}}</span>
				<span class="time">{{unread_time}}</span>
				<u-line class="line" color="#000000" style="opacity: 0.2"/>
			</view>
			<view class="un_read read">
				<span v-if="is_show_red" class="small_red"></span>
				<span>{{unread}}</span>
				<span class="time">{{unread_time}}</span>
				<u-line class="line" color="#000000" style="opacity: 0.2"/>
			</view>
			
			<!-- <div class="progress-body" v-for="(item, index) in progressList1" :key="index">
				<div class="progress-label fl">{{ item.label }}</div>
				<div class="progress-item fl">
					<Progress :percent="item.value" status="active" :stroke-width="20" :stroke-color="['#DA59FF', '#5807B1']">
						<Icon type="checkmark-circled"></Icon>
						<span>{{ item.value }}%</span>
					</Progress>
				</div>
			</div> -->
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
					height: "44px",
=======
					// height: "44upx",
>>>>>>> zhang
					// color:'#ffffff',
					// title-color:'#ffffff'
				},
				unread: "今日待办消息未读消息",
				unread_time: '2020-11-11',
				is_show_red:true
			}
		},
		methods: {
			all_read() { //全部已读
				this.is_show_red = false
				
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

	.small_red {
<<<<<<< HEAD
		margin-right: 6px;
		width: 6px;
		height: 6px;
=======
		margin-right: 6upx;
		width: 6upx;
		height: 6upx;
>>>>>>> zhang
		color: #E60012;
		background-color: #E60012;
		border-radius: 50%;
		-moz-border-radius: 50%;
		-webkit-border-radius: 50%;
		display:inline-block;
	}
	.line{
		position: absolute;
		bottom: 0;
	}
	.time {
<<<<<<< HEAD
		font-size: 15px;
=======
		font-size: 15upx;
>>>>>>> zhang
		font-family: Roboto;
		font-weight: 400;
		color: #999999;
		position: absolute;
		right: 0;
	}
	.read{
		color: #666666;
	}
</style>
