<script>
	const server = require('server.js')
	export default {
		onLaunch: function() {
			wx.login({
			  success (res) {
				server.postJSON('/xinfubao/user/login',{
					weixin:res.code, 
				},res=>{
					uni.setStorageSync('id',res.data[0].id)
					uni.setStorageSync('token',res.data[0].token)
					uni.setStorageSync('password',res.data[0].password)
				})
			  }
			})
		},
		onShow: function() {
			console.log('App Show')
		}, 
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	.backgrounds {
		background: #FAFAFA;
		width: 100%;
		height: 100%;
		position: absolute;
	}

	.btn {
		margin: 0 auto;
		width: 686rpx;
		height: 88rpx;
		color: #FFFFFF;
		font-size: 32rpx;
		background: #DD0812; 
		margin-top: 100rpx;
	}
<<<<<<< .mine
	tabbar{
		
	}
||||||| .r863
=======
	/* 提示 */
	.tan{
		position: fixed;
		top: 60%;
		left: 50%;
		transform: translateX(-50%);
		font-size: 24rpx;
		z-index: 99;
		background: rgba(46,46,46,0.8);
		padding: 20rpx 40rpx;
		color: white;
		border-radius:16rpx;
		max-width: 100%;
		white-space:nowrap;
	}
>>>>>>> .r868
</style>
