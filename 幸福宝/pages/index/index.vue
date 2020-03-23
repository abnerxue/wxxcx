<template>
	<view class="page">
		<view class="background">
			<image src="../../static/img/background.png"></image>
		</view>
		<view class="title">
			<image src="/static/img/title.png"></image>
		</view>
		<view class="ranking_list">
			<view class="ranking_lists">
				<swiper vertical="true" autoplay="true" circular="true" interval="3000" style="height: 60rpx;width: 536rpx;">
					<swiper-item>
						<view class="news">xx为医疗人员和病患捐助了1000个积分</view>
					</swiper-item>
					<swiper-item>
						<view class="news">xx为医疗人员和病患捐助了20个积分</view>
					</swiper-item>
				</swiper>
			</view>
		</view>
		<view class="main">
			<view class="zhuanpanbg">
				<view class="content" :animation="animationData" id="zhuanpano" style="">
					<image src="../../static/img/turntable.png"></image>
					<view class="canvas-list">
						<view class="canvas-item" :style="[{zIndex:index2}]" v-for="(iteml,index2) in awardsList" :key="index2">
							<view class="canvas-item-text" :style="[{transform:'rotate('+iteml.turn+')'}]">
								<view>{{iteml.award}}</view>
								<view>积分</view>
							</view>
						</view>
					</view>

				</view>
				<view @tap="playReward" class="canvas-btn" :class="btnDisabled">
					<image class="canvas-btn-pic" src="/static/img/golottery.png"></image>
				</view>
			</view>
			<view class=""></view>
		</view>
		<tabbar tags="2"></tabbar>
	</view>
</template>

<script>
	import tabbar from 'pages/tabbar/tabbar'
	const server = require('../../server');
	export default {
		data() {
			return {
				title: 'Hello',
				awardsList: [],
				awardsConfig: {
					lists: [{
							"id": 1,
							"type": 1, //1积分  2经验   3现金
							"name": "1点", //名称
							"amount": "1.00", //数额
							"scale": "0.10", //中奖比例
							"createtime": 1553651469
						},
						{
							"id": 2,
							"type": 1, //1积分  2经验   3现金
							"name": "2点", //名称
							"amount": "1.00", //数额
							"scale": "0.10", //中奖比例
							"createtime": 1553651469
						},
						{
							"id": 3,
							"type": 1, //1积分  2经验  3现金
							"name": "3点", //名称
							"amount": "1.00", //数额
							"scale": "0.10", //中奖比例
							"createtime": 1553651469
						},
						{
							"id": 4,
							"type": 1, //1积分  2经验   3现金
							"name": "4点", //名称
							"amount": "1.00", //数额
							"scale": "0.10", //中奖比例
							"createtime": 1553651469
						},
						{
							"id": 5,
							"type": 1, //1积分  2经验   3现金
							"name": "5点", //名称
							"amount": "1.00", //数额
							"scale": "0.10", //中奖比例
							"createtime": 1553651469
						},
						{
							"id": 6,
							"type": 1, //1积分  2经验   3现金
							"name": "6点", //名称
							"amount": "6.00", //数额
							"scale": "0.10", //中奖比例
							"createtime": 1553651469
						},
						{
							"id": 7,
							"type": 1, //1积分  2经验   3现金
							"name": "10点", //名称
							"amount": "1.00", //数额
							"scale": "0.20", //中奖比例
							"createtime": 1553651469
						},
						{
							"id": 8,
							"type": 1, //1积分  2经验   3现金
							"name": "11点", //名称
							"amount": "6.00", //数额
							"scale": "0.20", //中奖比例
							"createtime": 1553651469
						},
					], //奖品列表 
				},
				animationData: {}, //动画数据
				btnDisabled: '', //按钮是否禁用
				chance: 0, //次数
			}
		},
		components: {
			tabbar
		},
		onLoad() {
			let that = this;
			server.postJSON(
				'/xinfubao/prize/info', {
					aid: 1,
					userId: uni.getStorageSync('id')
				},res => {
					console.log(res.data)
					res.data.map((item,i) => {
						that.awardsConfig.lists[i].name = item.prize + '点';
					});
					this.initdata(this)
				}
			);
			// 获取奖品列表
			
		},
		methods: {
			initdata(that) {
				that.chance = 100;
				// 获取奖品的个数
				let awarrlength = that.awardsConfig.lists.length
				// 为每一项追加index属性
				that.awardsConfig.lists.forEach(function(element, index) {
					element.index = index
				})
				// 画转盘
				that.drawAwardRoundel();
				// }
				// })
			},
			//画抽奖圆盘
			drawAwardRoundel() {
				// 拿到奖品列表
				let awards = this.awardsConfig.lists;
				let awardsList = [];
				// 每份奖品所占角度
				let turnNum = 1 / awards.length * 360; // 文字旋转 turn 值  
				// 奖项列表  
				for (let i = 0; i < awards.length; i++) {
					awardsList.push({
						turn: i * turnNum + turnNum / 2 + 'deg', //每个奖品块旋转的角度
						lineTurn: i * turnNum + 'deg', //奖品分割线的旋转角度
						award: awards[i].name, //奖品的名字,
						type: awards[i].type,
						id: awards[i].type,
					});
				}
				this.btnDisabled = this.chance ? '' : 'disabled';
				this.awardsList = awardsList;
			},
			//发起抽奖
			playReward() {
				let that = this
				// that.runDeg = 60*Math.random()
				if (this.chance == 0) {
					uni.showToast({
						title: '抽奖次数已经用完',
						icon: 'none'
					})
					return
				}
				let id;
				// 中奖假数据
				let data = {
					"id": 4,
					"user_id": 3,
					"name": "111", //标题
					"number": 2, //数额
					"type": 1, //1积分  2经验   3现金
					"createtime": 1553652319,
				};
				server.postJSON('/xinfubao/prize/lottery', {
					aid: 1,
					userId: uni.getStorageSync('id')
				}, res => {
					id = res.data[0].id;
					console.log(res)
					let awardIndex = 0; //中奖index，0为谢谢参与
					that.awardsList.forEach((element, index) => {
						if (element.award == data.name) {
							awardIndex = index
						}
					})
					//设置旋转时长及周数
					console.log(id,(id/8));
					let awardsNum = that.awardsConfig.lists;
					let runNum = 4-(id/8); //旋转8周  
					
					let duration = 4000; //时长  
					// 旋转角度  
					that.runDeg = that.runDeg || 0;
					let preDeg = that.runDeg;
					that.runDeg = that.runDeg + (360 - that.runDeg % 360) + (360 * runNum - awardIndex * (
						360 / awardsNum.length)) + 1;
					let animationRun = uni.createAnimation({
						duration: duration,
						timingFunction: 'ease'
					})
					animationRun.rotate(that.runDeg).step();
					that.animationData = animationRun.export();
					that.btnDisabled = 'disabled';
					// 中奖提示  
					let awardsConfig = that.awardsConfig;
					let awardType = awardsConfig.lists[awardIndex].type;
					that.chance = that.chance - 1;
					setTimeout(() => {
						uni.showModal({
							title: '恭喜',
							content: '获得' + res.data[0].prize + '积分',
							showCancel: false,
							success: function() {
								// 置空style  否则动画不生效
								// setTimeout(function(){
								// document.getElementById('zhuanpano').style=''
								// },1000)
							}
						});
						that.btnDisabled = '';
					}, duration);
				})
				// );
				// 抽奖接口
				// this.$api.startLuckyDraw({
				// 	cmd: {},
				// 	data: {}
				// }).then(res=>{
				// 	if(res.code === 200) {
				// let data = res.data;
				

				// 	}
				// })

			},
		}
	}
</script>

<style>
	.page {
		width: 750upx;
		flex: 1;
		overflow-x: hidden;
		overflow-y: scroll;
	}

	.background image {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
	}

	.title {
		position: absolute;
		top: 50rpx;
		z-index: 400;
		height: 106rpx;
		width: 100%;
		text-align: center;
	}

	.title image {
		width: 560rpx;
		height: 106rpx;
		/* z-index: 400; */
	}

	.ranking_list {
		display: flex;
		width: 100%;
		font-size: 24rpx;
		color: #FFFFFF;
		justify-content: center;
		margin-top: 180rpx;
		z-index: 4;
	}

	.ranking_lists {
		width: 510rpx;
		height: 60rpx;
		border-radius: 30rpx;
		text-align: center;
		line-height: 60rpx;
		background: #DE342F;
		z-index: 4;
	}

	.main {
		margin-top: 16rpx;
	}

	.zhuanpanbg {
		margin: 0 auto;
		position: relative;
		width: 638rpx;
		height: 638rpx;
		border-radius: 50%;
		/* background-color: #333333; */
	}

	.content {
		/* background: url(../../static/img/turntable.png) no-repeat; */
		background-size: 638rpx 638rpx;
		position: absolute;
		left: 0;
		top: 0;
		z-index: 1;
		display: block;
		width: 638rpx;
		height: 638rpx;
		border-radius: inherit;
	}

	.content image {
		width: 638rpx;
		height: 638rpx;
	}

	.canvas-list {
		position: absolute;
		left: 0;
		top: 0;
		width: inherit;
		height: inherit;
		z-index: 500;
	}

	.canvas-item {
		position: absolute;
		left: 0;
		top: -28rpx;
		width: 100%;
		height: 100%;
		color: #e4370e;
	}

	.canvas-item-text {
		position: relative;
		display: block;
		padding-top: 160rpx;
		margin: 0 auto;
		text-align: center;
		-webkit-transform-origin: 50% 340rpx;
		transform-origin: 50% 340rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
		color: #F20B2E;
		font-size: 24rpx;
		z-index: 500;
	}

	/* .* 抽奖按钮 */
	.canvas-btn {
		position: absolute;
		display: block;
		border-radius: 50%;
		overflow: hidden;
		left: 256rpx;
		top: 220rpx;
		z-index: 400;
		width: 126rpx;
		height: 154rpx;

	}

	.canvas-btn-pic {
		width: 126rpx;
		height: 154rpx;
	}

	.canvas-btn .disabled {
		pointer-events: none;
		color: #ccc;
	}
</style>
