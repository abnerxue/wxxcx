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
					<image src="../../static/click.png" style="width: 40rpx;height: 40rpx;"></image>
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
	<!-- <view class="bottomtabs">
		<view class="bottomtab">
			<navigator class="bottabbar" :class="tags==1? 'actives' : '' " open-type="redirect" url="../story/story">
				<image src="../../static/书 (1)@3x.png" class="ims" v-if="tags==1"></image>
				<image src="../../static/书 (2)@3x.png" class="ims" v-else></image>
				<view>故事</view>
			</navigator>
			<navigator class="bottabbar" :class="tags==2 ? 'actives' : '' "  open-type="redirect" url="../index/index">
				<view class="radiu"></view>
				<view>点点乐</view>
			</navigator>
			<navigator class="bottabbar" :class="tags==3 ? 'actives' : '' "  open-type="redirect" url="../user/user">
				<image src="../../static/我的@3x.png" class="ims" v-if="tags==3"></image>
				<image src="../../static/我的@3x (2).png" class="ims" v-else></image>
				<view>我的</view>
			</navigator>
		</view>
	</view> -->
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
		width: 100%;
		height: 124rpx;
		background: #FFFFFF;
		position: fixed;
		font-size: 26rpx;
		bottom: 0;
		z-index:400 ;
	}
	.bottomtab{
		margin-top: 10rpx;
		margin-left: 105rpx;
		width: 540rpx;
		justify-content: space-between;	
		display: flex;
	}
	.bottabbar{
		display: flex;
		flex-direction: column;
		/* width: 100rpx; */
	}
	.ims {
		width: 40rpx;
		height: 40rpx;
	}
	/* .bottomtabs{
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
	} */
	/* .radiu{
		width: 108rpx;
		height: 108rpx;
		border-radius: 108rpx;
		background: white;
		position: absolute;
		top: -20rpx;
	} */
</style>
