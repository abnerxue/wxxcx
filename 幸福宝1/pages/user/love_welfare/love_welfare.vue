<template>
	<view class="backgrounds">
		<navigator class="back_image" open-type="navigate" :url="'thelist/thelist?id='+data[0].id">
			<text class="title">{{data.name}}</text>
		</navigator>
		<image :src="data.img" class="backgroundimage"></image>
		<view class="content_list">
			<navigator class="content" v-for="datas in datas" open-type="navigate" :url="'thelist/thelist?id='+datas.id">
				<image class="content_image" :src="datas.img"></image>
				<view class="content_font">{{datas.name}}</view>
			</navigator>
		</view>
	</view>
</template>

<script>
	const server = require('../../../server');
	export default {
		data() {
			return {
				data:[],
				datas:[]
			}
		},
		onLoad() {
			let that = this;
			server.postJSON('/xinfubao/give/activity/info',{
				userId:uni.getStorageSync('id'),
			},res=>{
				for(var i in res.data){
					if(i==0){
						that.data.push(res.data[i])
					}else{
						that.datas.push(res.data[i])
					}
				}
			})
		},
		methods:{
			
		}
	}
</script>

<style>
.back_image{
	width: 100%;
	height: 421.88rpx;
	display: flex;
	align-items: center;
	color: white;
	font-size: 60rpx;
	z-index:50;
	position: relative;
	justify-content: center;
}
.backgroundimage{
	position: absolute;
	top:0;
	width: 100%;
	height: 421.88rpx;
	
}
.title{
	margin: 0 30rpx;
}
.content_list{
	width: 100%;
	padding: 20rpx 32rpx 0;
	display: flex;
	box-sizing: border-box;
	flex-wrap: wrap;
	justify-content: space-between;
}
.content{
	width: 327rpx;
	height: 288rpx;
	background: white;
	display: flex;
	flex-direction: column;
	margin-bottom: 20rpx;
	border-radius: 10rpx;
	box-shadow: 0 4rpx 16rpx #EDEBEB;
}
.content_image{
	width: 100%;
	height: 216rpx;
}
.content_font{
	width: 100%;
	height: 72rpx;
	padding-left: 20rpx;
	font-size: 28rpx;
	color: #333333;
	display: flex;
	align-items: center;
	box-sizing: border-box;
}
</style>
