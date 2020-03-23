<template>
	<view class="back">
		<view class="integral">
			<navigator class="cornermark" open-type="navigate" url="details/details">明细</navigator>
			<view class="title">我的可用积分</view>
			<view class="balance">{{data.score}}</view>
			<view>已推荐人数：82人</view>
			<view class="tab">
				<navigator class="tabs"  open-type="navigate" url="../mall/mall">
					<image src="../../../static/cart.png"  class="cart"></image>
					<text>商城消费</text>
				</navigator>
				<view class="borders"></view>
				<navigator class="tabs" open-type="navigate" url="../love_welfare/love_welfare">
					<image src="../../../static/xin.png" class="iconsxin"></image>
					<text>爱心公益</text>
				</navigator>
			</view>
		</view>
		<view class="rules">
			<view class="rule">规则：</view>
			<view class="rule">1. 积分可进入杏福宝商城使用</view>
			<view>2. 积分可以100：1的价值捐赠与爱心机构</view>
		</view>
	</view>
</template>

<script>
	const server = require('../../../server');
	export default {
		data() {
			return {
				data:[]
			}
		},
		onLoad() {
			let that = this;
			server.postJSON('/xinfubao/score/info',{
				userId:uni.getStorageSync('id')
			},res=>{
				that.data = res.data[0]
			})
		},
		methods: {
			
		}
	}
</script>

<style>
.back{
	padding: 16rpx 32rpx;
	box-sizing: border-box;
}
.integral{
	width: 100%;
	height: 364rpx;
	box-shadow: 0 4rpx 16rpx #EDEBEB;
	border-radius: 10rpx;
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
	font-size: 26rpx;
	color: #999999;
}
.cornermark{
	background: url(../../../static/mark.png) no-repeat;
	background-size:100%;
	position: absolute;
	top: 0;
	right: 0;
	width: 112rpx;
	height: 48rpx;
	font-size: 26rpx;
	color: white;
	text-align: center;
	line-height: 48rpx;
	padding-left: 10rpx;
	box-sizing: border-box;
}
.title{
	margin: 30rpx 0 20rpx;
	color: #666666;
}
.cart{
	width: 31rpx; 
	height: 31.46rpx;
	margin-right: 16rpx;
}
.iconsxin{
	width: 36.75rpx;
	height: 36.75rpx;
	margin-right: 16rpx;
}
.balance{
	color: #333333;
	font-size: 45rpx;
	margin-bottom: 46rpx;
}
.tab{
	position: absolute;
	bottom: 0;
	width: 100%;
	display: flex;
	padding: 0 30rpx;
	box-sizing: border-box;
	justify-content: space-around;
	height: 110rpx;
	align-items: center;
}
.tabs{
	display: flex;
	align-items: center;
}
.borders{
	height: 70%;
	width: 2rpx;
	background-color: #DEDEDE;
}
.rules{
	font-size: 24rpx;
	color: #999999;
	margin: 50rpx 30rpx 0;
}
.rule{
	margin-bottom:10rpx;
}
</style>
