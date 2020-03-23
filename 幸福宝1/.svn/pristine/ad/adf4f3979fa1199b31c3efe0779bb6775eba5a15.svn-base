<template>
	<view class="bottomtabs">
		<view class="bottomtab">
			<navigator class="bottabbar" :class="tags==1? 'actives' : '' " open-type="redirect" url="../story/story">
				<image src="../../static/书 (1)@3x.png" class="ims" v-if="tags==1"></image>
				<image src="../../static/书 (2)@3x.png" class="ims" v-else></image>
				<view>故事</view>
			</navigator>
			<navigator class="bottabbar" :class="tags==2 ? 'actives' : '' "  open-type="redirect" url="../index/index">
				<view class="radiu">
					<image v-if="tags!=2" src="../../static/16.png" mode=""></image>
					<image v-else src="../../static/15.png" mode=""></image>
				</view>
				<view>点点乐</view>
			</navigator>
			<navigator class="bottabbar" :class="tags==3 ? 'actives' : '' "  open-type="redirect" url="../user/user">
				<image src="../../static/我的@3x.png" class="ims" v-if="tags==3"></image>
				<image src="../../static/我的@3x (2).png" class="ims" v-else></image>
				<view>我的</view>
			</navigator>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		props: ["tags"],
		onLoad() {
		},
		methods: {
			home() {
				
			},
			classfy() {
				
			},
			user() {
				
			}
		}
	}
</script>

<style>
	.bottomtabs{
		position: relative;
		width: 100%;
		height: 100rpx;
	}
	.bottomtab {
		position: fixed;
		bottom: 0;
		width: 100%;
		height: 100rpx;
		display: flex;
		justify-content: space-around;
		background: white;
		z-index: 55;
	}

	.bottabbar {
		height: 100%;
		width: 180rpx;
		font-size: 24rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
		flex-direction: column;
		padding: 14rpx 0;
		box-sizing: border-box;
	}

	.ims {
		width: 40rpx;
		height: 40rpx;
	}

	.actives {
		color: #74181B;
		position: relative;
	}
	.bottabbar:nth-child(2) view:nth-child(2){
		position: absolute;
		z-index: 1;
		bottom: 14rpx;
	}
	.radiu{
		width: 108rpx;
		height: 108rpx;
		border-radius: 50%;
		background: white;
		position: absolute;
		top: -30rpx;
		left: 0;
		right: 0;
		margin: 0 auto;
		z-index: 0;
		text-align: center;
	}
	.radiu image{
		width: 72rpx;
		height: 72rpx;
		border-radius: 50%;
		margin-top: 12rpx;
	}
</style>
