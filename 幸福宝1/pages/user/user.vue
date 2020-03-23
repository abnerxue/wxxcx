<template>
	<view  class="backgrounds">
		<view class="avatar">
			<view class="head">
				<image :src="userInfo.avatarUrl"></image>
				<view class="name">{{userInfo.nickName}}</view>
			</view>
		</view>
		<view class="list">
			<navigator class="options options-border" open-type="navigate" url="integral/integral">
				<view class="iconsfont"><image src="../../static/bottoms.png" class="icons"></image><text>积分</text></view>
				<image src="../../static/right.png" class="rgith"></image>
			</navigator>
			<navigator class="options options-border" open-type="navigate" url="love_welfare/love_welfare">
				<view class="iconsfont"><image src="../../static/xin.png" class="iconsxin"></image><text>爱心公益</text></view>
				<image src="../../static/right.png" class="rgith"></image>
			</navigator>
			<navigator class="options options-bottom"  open-type="navigate" url="mall/mall">
				<view class="iconsfont"><image src="../../static/cart.png" class="cart"></image><text>商城消费</text></view>
				<image src="../../static/right.png" class="rgith"></image>
			</navigator>
			<navigator class="options options-bottom" open-type="navigate" url="download/download">
				<view class="iconsfont"><image src="../../static/bottom.png" class="bottom"></image><text>杏福宝下载</text></view>
				<image src="../../static/right.png" class="rgith"></image>
			</navigator>
			<navigator class="options" open-type="navigate" url="revise_password/revise_password">
				<view class="iconsfont"><image src="../../static/shuo.png" class="shuo"></image><text>修改支付密码</text></view>
				<image src="../../static/right.png" class="rgith"></image>
			</navigator>
		</view>
		<tabbar tags="3"></tabbar>
	</view>
</template>

<script>
	import tabbar from 'pages/tabbar/tabbar'
	export default {
		data() {
			return {
				userInfo:{},//用户信息
			}
		},
		components:{
			tabbar
		},
		onLoad() {
			this.userInfo = uni.getStorageSync('userInfo');
		},
		methods: {
			
		}
	}
</script>

<style>

.avatar{
	width: 100%;
	height: 336rpx;
	background: url(../../static/acatar.jpg);
	background-size: 100%;
	display:flex;
	align-items: center;
	justify-content: center;
	padding: 50rpx 0;
	box-sizing: border-box;
}
.head{
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: space-between;
	height: 100%;
}
.head image{
	width: 156rpx;
	height: 156rpx;
	border-radius: 156rpx;
}
.name{
	font-size: 34rpx;
	color: white;
}
.options{
	width: 100%;
	height: 88rpx;
	background: #FFFFFF;
	display: flex;
	padding: 0 36rpx;
	box-sizing: border-box;
	align-items: center;
	justify-content: space-between;
	font-size: 28rpx;
	color: #333333;
}
.options-border{
	border-bottom: 2rpx solid #F8F8F8;
}
.iconsfont{
	display: flex;
	align-items: center;
}
.rgith{
	width: 12.43rpx;
	height: 20.14rpx;
}
.icons{
	width: 39rpx;
	height: 32rpx;
	margin-right: 20rpx;
}
.iconsxin{
	width: 36.75rpx;
	height: 36.75rpx;
	margin-right: 20rpx;
}
.cart{
	width: 31rpx;
	height: 31.46rpx;
	margin-right: 20rpx;
}
.bottom{
	width: 35.99rpx;
	height: 35.23rpx;
	margin-right: 20rpx;
}
.shuo{
	width: 31.94rpx;
	height: 33.33rpx;
	margin-right: 20rpx;
}
.options-bottom{
	margin-bottom: 20rpx;
}
</style>
