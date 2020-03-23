<template>
	<view class="backgrounds">
		<view class="head_tab">
			<view class="heads_tab">
				<view :class="tab==0?'active':''" @click="tab=0">{{data.title}}</view>
				<view :class="tab==1?'active':''" @click="the_list">捐助榜单</view>
			</view>
		</view>
		<view class="content">
			<view class="swiper">
				<view class="swiper_list">
					<view>90**抽中了20紫薇币</view>
					<view>刚刚</view>
				</view>
				<view class="swiper_list">
					<view>90**抽中了20紫薇币</view>
					<view>刚刚</view>
				</view>
			</view>
		</view>
		<view class="contents" v-show="tab==0" v-html="data.content">
			
		</view>
		<view v-show="tab==1">
			<view class="list_content" v-for="(data,index) in thelist"> 
				<view class="list_icon">
					<image class="list_content_img" src="../../../../static/gold.png" v-if="index==0"></image>
					<image class="list_content_img" src="../../../../static/silver.png" v-if="index==1"></image>
					<image class="list_content_img" src="../../../../static/copper.png" v-if="index==2"></image>
					<view v-if="index>2" class="list_content_img">
						{{index}}
					</view>
					<view class="userinfor">
						<view class="name">{{data.userName}}</view>
						<view class="time">{{data.time}}</view>
					</view>
				</view>
				<view>{{data.score}}积分</view>
			</view>
		</view>
		<view class="bottom_btn">
			<view class="bottom_btns">
				<button class="btns" @click="donation">我要捐款</button>              
			</view>
		</view>
	</view>
</template>

<script>
	const server = require('../../../../server');
	export default {
		data() {
			return {
				tab:0,//顶部tab  0 聚焦疫情   1 捐助榜单
				data:{},
				id:0,
				thelist:[]
			}
		},
		onLoad(option) {
			this.id = option.id
			server.postJSON('/xinfubao/article/info',{
				id:option.id,
				userId:uni.getStorageSync('id')
			},res=>{
				this.data = res.data[0]
			})
		},
		methods: {
			the_list(){
				let that = this;
				this.tab=1
				server.postJSON('/xinfubao/give/score/info',{
					aid:that.id,
					userId:uni.getStorageSync('id')
				},res=>{
					this.thelist = res.data
				})
			},
			donation(){
				uni.navigateTo({
					url:'donation/donation'
				})
			}
		}
	}
</script>

<style>
.head_tab{
	position: relative;
	width: 100%;
	height: 88rpx;
	
}
.heads_tab{
	z-index: 55;
	position: fixed;
	background: white;
	display: flex;
	justify-content: space-around;
	align-items: center;
	width: 100%;
	height: 88rpx;
	color: #999999;
	font-size: 28rpx;
}
.heads_tab view{
	height: 88rpx;
	width: 120rpx;
	line-height: 88rpx;
	text-align: center;
	white-space: nowrap;
	overflow: hidden;
	text-overflow: ellipsis;
}
.active{
	color: #161616;
	
	border-bottom: 2px solid #DE342F;
}
.content{
	padding:20rpx 32rpx;
	box-sizing: border-box;
}
.swiper{
	width: 100%;
	height: 132rpx;
	background: white;
	padding: 24rpx;
	box-sizing: border-box;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	border-radius: 10rpx;
	font-size: 24rpx;
}
.swiper_list{
	display: flex;
	justify-content: space-between;
}
.bottom_btn{
	position: relative;
	width: 100%;
	height: 128rpx;
}
.bottom_btns{
	position: fixed;
	width: 100%;
	height: 128rpx;
	display: flex;
	align-items: center;
	justify-content: center;
	background: white;
	bottom: 0;
}
.btns{
	background: #DD0812;
	width: 686rpx;
	height: 88rpx;
	text-align: center;
	line-height: 88rpx;
	color: #FFFFFF;
	font-size: 32rpx;
}
.contents{
	display: flex;
	flex-direction: column;
	padding:0 32rpx;
	box-sizing: border-box;
	background: #FAFAFA;
}
.image{
	width: 100%;
	height: 385.88rpx;
}
.images{
	height: 500px;
	margin: 0 auto;
}
.imagess{
	margin: 0 auto;
}
.imagesss{
	width: 100%;
	margin: 0 auto;
}
.font{
	color: #333333;
	font-size: 28rpx;
	margin-top: 26rpx;
	text-indent:25px;
}
.fonts{
	color: #333333;
	font-size: 28rpx;
	text-indent:25px;
}
.images-list{
	width: 100%;
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
}
.list_content{
	width: 100%;
	height: 132rpx;
	border-bottom: 1rpx solid #FAFAFA;
	display: flex;
	padding:0 30rpx;
	box-sizing: border-box;
	align-items: center;
	font-size: 30rpx;
	color: #333333;
	justify-content: space-between;
	background: white;
}
.list_content_img{
	width: 60rpx;
	height: 60rpx;
	margin-right: 30rpx;
	display: flex;
	justify-content: center;
	align-items: center;
}
.list_icon{
	display: flex;
	align-items: center;
}
.userinfor{
	display: flex;
	flex-direction: column;
}
.time{
	margin-top: 16rpx;
	font-size: 24rpx;
	color: #999999;
}
</style>
