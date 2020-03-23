<template>
	<view class="backgrounds">
		<view class="back">
			<view class="title">{{content.title}}</view>
			<view class="content" v-html="content.content">
				
			</view>
		</view>
		<tabbar tags="1"></tabbar>
	</view>
</template>

<script>
	import tabbar from 'pages/tabbar/tabbar'
	const server = require('../../server');
	export default {
		data() {
			return {
				content:{}
			}
		},
		components:{
			tabbar
		},
		onLoad() {
			let that = this;
			server.postJSON('/xinfubao/article/info',{
				id:1,
				userId:uni.getStorageSync('id')
			},res=>{
				this.content = res.data[0]
			})
		},
		methods: {
			
		}
	}
</script>

<style>
.back{
	background: #FAFAFA;
	width: 100%;
	padding:0 30rpx 30rpx;
	box-sizing: border-box;
}
.title{
	color: #333333;
	font-size: 30rpx;
	text-align: center;
	margin: 30rpx 0;
}
.content{
	display: flex;
	flex-direction: column;
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
</style>
