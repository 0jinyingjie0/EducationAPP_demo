<!-- 修改手机号码页面 -->
<template>
	<view class="body">
<<<<<<< HEAD
		<u-navbar :is-back="true" title="课程" title-color="#333333" title-size="18px"  :background="background">
=======
		<u-navbar :is-back="true" title="课程" title-color="#333333" title-size="36upx"  :background="background">
>>>>>>> zhang
		</u-navbar>
		<view class="tab_info">
			<span class="school_title">{{school.title}}</span>
			<span class="school_semester" >{{school.semester}}</span>
			<view class="school_time">{{school.time}}</view>
<<<<<<< HEAD
			<view class="school_tab" @click="change_term()">
=======
			<view class="school_tab">
>>>>>>> zhang
				<image class="school_icon" src="../../static/qiehuan.png" mode=""></image>
				<view class="school_icon_word">切换</view>
			</view>
		</view>
		<view class="container">
			<u-tabs class="tab" :list="list" height="100" active-color="#43B4AE" font-size="16rpx" :is-scroll="false" :current="current" @change="change"></u-tabs>
			<u-line class="line" color="#000000" style="opacity: 0.2"/>
			
			<view class="in_mend">
				<view class="item_lesson" @click="toCourseDetaile">
					<span>
						<image class="book_picture" src="../../static/book.png" mode=""></image>
					</span>
					<span>
<<<<<<< HEAD
						<view class="book" >
=======
						<view class="book">
>>>>>>> zhang
							<view class="title_img">
								<view class="book_title">{{book.title}}</view>
								<view class="book_status">
									<image class="status_img" src="../../static/zaixiu@2x.png" mode=""></image>
								</view>
								
							</view>
							<view class="book_exam">{{book.exam}}</view>
							<view class="book_exam">课程已学习{{book.plan}}%</view>
							<u-line-progress active-color="#44B4AE" height="8" :show-percent="false"  :round="true" :percent="book.plan"></u-line-progress>
						</view>
						
					</span>
					<u-line class="line" color="#000000" style="opacity: 0.2"/>
				</view>
				<view class="item_lesson">
					<span>
						<image class="book_picture" src="../../static/book.png" mode=""></image>
					</span>
					<span>
						<view class="book">
							<view class="title_img">
								<view class="book_title">{{book.title}}</view>
								<view class="book_status">
									<image class="status_img" src="../../static/zaixiu@2x.png" mode=""></image>
								</view>
								
							</view>
							<view class="book_exam">{{book.exam}}</view>
							<view class="book_exam">课程已学习{{book.plan}}%</view>
							<u-line-progress active-color="#44B4AE" height="8" :show-percent="false"  :round="true" :percent="book.plan"></u-line-progress>
						</view>
						
					</span>
					<u-line class="line" color="#000000" style="opacity: 0.2"/>
				</view>
				<view class="item_lesson">
					<span>
						<image class="book_picture" src="../../static/book.png" mode=""></image>
					</span>
					<span>
						<view class="book">
							<view class="title_img">
								<view class="book_title">{{book.title}}</view>
								<view class="book_status">
									<image class="status_img" src="../../static/zaixiu@2x.png" mode=""></image>
								</view>
								
							</view>
							<view class="book_exam">{{book.exam}}</view>
							<view class="book_exam">课程已学习{{book.plan}}%</view>
							<u-line-progress active-color="#44B4AE" height="8" :show-percent="false"  :round="true" :percent="book.plan"></u-line-progress>
						</view>
						
					</span>
					<u-line class="line" color="#000000" style="opacity: 0.2"/>
				</view>
			</view>
		</view>
		<u-modal v-model="show" negative-top='650'   :content="content"></u-modal>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: {
					backgroundColor: '#ffffff',
<<<<<<< HEAD
					height: "44px",
=======
					height: "88upx",
>>>>>>> zhang
					
				},
				school:{
					title:"遵义职业技术学院",
					semester:'当前学期',
					time:'2020.06.01-2020.12.15',
				},
				book:{
					title:'经济学基础',
					status:'已完成',
					plan:40,
					exam:'暂无考试安排'
				},
				list: [{
						name: '在修课程'
					}, {
						name: '已修完课程',
						count: 1
					}, 
				],
				current: 0,
				show: false,
				content: '东临碣石，以观沧海'
			}
		},
		methods: {
			change(index) {
				this.current = index;
			},
			change_term(){
				this.show = true;
				console.log("222")
			},
<<<<<<< HEAD
			toCourseDetaile(){
=======
				toCourseDetaile(){
>>>>>>> zhang
				console.log("####");
				uni.navigateTo({
					url:"../courseModule/enterCourse"
				})
			}
		}
	}
</script>

<<<<<<< HEAD
<style>
	/deep/ .u-tab-bar[data-v-3b2b1a80] {
		position: absolute;
		bottom: -3px;
	}
	.body{
		width: 375px;
=======
<style lang="scss" scoped>
	/deep/ .u-tab-bar[data-v-3b2b1a80] {
		position: absolute;
		bottom: -6upx;
	}
	.body{
		width: 100%;
>>>>>>> zhang
		background-color: rgba(229, 227, 227, 0.16);
	}
	.tab_info{
		background-color: #FFFFFF;
<<<<<<< HEAD
		height: 90px;
		padding: 19px 26px 16px 15px;		
		position: relative;
	}
	.school_title{
		height: 15px;
		font-size: 15px;
=======
		height: 180upx;
		padding: 40upx 52upx 32upx 30upx;		
		position: relative;
	}
	.school_title{
		height: 30upx;
		font-size: 30upx;
>>>>>>> zhang
		font-family: PingFang SC;
		font-weight: bold;
		color: #333333;
	}
	.school_semester{
<<<<<<< HEAD
		height: 12px;
		font-size: 12px;
		font-family: PingFang SC;
		font-weight: 500;
		color: #999999;
		margin-left: 10px;
	}
	.school_time{
		width: 150px;
		height: 25px;
		line-height: 25px;
		text-align: center;
		font-size: 12px;
=======
		height: 24upx;
		font-size: 24upx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #999999;
		margin-left: 20upx;
	}
	.school_time{
		width: 300upx;
		height: 50upx;
		line-height: 50upx;
		text-align: center;
		font-size: 24upx;
>>>>>>> zhang
		font-family: PingFang SC;
		font-weight: 500;
		color: #999999;
		background-color: #F8F8F8;
<<<<<<< HEAD
		border-radius: 12.5px;
		margin-top: 15px;
	}
	.school_tab{
		position: absolute;
		top: 19px;
		right: 26px;
	}
	.school_icon{
		width: 22.5px;
		height: 22.5px;
	}
	.school_icon_word{
		font-size: 11px;
=======
		border-radius: 25upx;
		margin-top: 30upx;
	}
	.school_tab{
		position: absolute;
		top: 40upx;
		right: 52upx;
	}
	.school_icon{
		width: 45upx;
		height: 45upx;
	}
	.school_icon_word{
		font-size: 22upx;
>>>>>>> zhang
		font-family: PingFang SC;
		font-weight: bold;
		color: #E92222;
	}
	.item_lesson{
<<<<<<< HEAD
		height: 140px;
		/* margin-top: 8px; */
	}
	.in_mend{
		width: 375px;
		padding: 0px 20px 0px 15px;
		background-color: #ffffff;
	}
	.book_picture{
		width: 70px;
		height: 100px;
		float: left;
		margin: 20px 0 20px 0;
	}
	.book{
		float: left;
		margin-left: 15px;
		width: 240px;
	}
	.book_title{
		/* width: 147px; */
		height: 15px;
		font-size: 15px;
		font-family: PingFang SC;
		font-weight: 500;
		color: #333333;
		margin-top: 10px;
=======
		height: 280upx;
		/* margin-top: 8px; */
	}
	.in_mend{
		width: 750upx;
		padding: 0px 40upx 0px 30upx;
		background-color: #ffffff;
	}
	.book_picture{
		width: 140upx;
		height: 200upx;
		float: left;
		margin: 40upx 0 40upx 0;
	}
	.book{
		float: left;
		margin-left: 30upx;
		width: 480upx;
	}
	.book_title{
		/* width: 147px; */
		height: 30upx;
		font-size: 30upx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #333333;
		margin-top: 20upx;
>>>>>>> zhang
		float: left;
	}
	.book_status{
		float: left;
<<<<<<< HEAD
		margin-left: 10px;
	}
	.title_img{
		height: 25px;
	}
	.status_img{
		width: 40px;
		height: 18px;
		margin-top: 11px;
	}
	.book_exam{
		/* width: 154px; */
		height: 13px;
		font-size: 13px;
		font-family: PingFang SC;
		font-weight: 500;
		color: #999999;
		margin-top: 10px;
	}
	.line{
		margin-bottom: 25px;
=======
		margin-left: 20upx;
	}
	.title_img{
		height: 50upx;
	}
	.status_img{
		width: 80upx;
		height: 36upx;
		margin-top: 22upx;
	}
	.book_exam{
		/* width: 154px; */
		height: 26upx;
		font-size: 26upx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #999999;
		margin-top: 20upx;
	}
	.line{
		margin-bottom: 50upx;
>>>>>>> zhang
	}
</style>
