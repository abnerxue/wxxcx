<template>
	<view class="backgrounds">
		<view class="back">
			<view class="details">
				<view class="details-name">
					<view>爱心公益捐赠</view>
					<view class="time">2019-12-01</view>
				</view>
				<view>-1000</view>
			</view>
			<view class="details">
				<view class="details-name">
					<view>爱心公益捐赠</view>
					<view class="time">2019-12-01</view>
				</view>
				<view>-1000</view>
			</view>
			<view class="details">
				<view class="details-name">
					<view>爱心公益捐赠</view>
					<view class="time">2019-12-01</view>
				</view>
				<view>-1000</view>
			</view>
		</view>
	</view>
</template>

<script>
	const server = require('../../../../server');
	export default {
		data() {
			return {
				data:[]
			}
		},
		onLoad() {
			let that = this;
			server.postJSON('/xinfubao/give/score/usergives',{
				userId:uni.getStorageSync('id')
			},res=>{
				console.log(res)
				that.data = res.data[0]
			})
		},
		methods: {
			
		}
	}
</script>

<style>
.back{
	background: #FAFAFA;
}
.details{
	border-top: 1rpx solid #DEDEDE;
	width: 100%;
	height: 120rpx;
	display: flex;
	justify-content: space-between;
	padding: 0 30rpx; 
	box-sizing: border-box;
	align-items: center;
	font-size: 30rpx;
	color: #333333;
	background: #FFFFFF;
}
.details-name{
	display: flex;
	flex-direction: column;
	text-align: center;
}
.time{
	color: #999999;
	font-size: 24rpx;
}
.details-name view{
	margin: 6rpx 0;
}
</style>
