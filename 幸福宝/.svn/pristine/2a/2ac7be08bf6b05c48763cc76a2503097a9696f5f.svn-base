<template>
	<view class="backgrounds">
		<view class="tan" v-show="tan">
			<text>{{message}}</text>
		</view>
		<view class="inputs">
			<view class="input">
				<text>{{name}}：</text>
				<input :type="types" class="inpus" v-model="val">
			</view>
			<image class="icon" src="../../../static/examine.png" v-show="examines==false" @click="exmain(1)"></image>
			<image class="icon" src="../../../static/examine1.png" v-show="examines==true" @click="exmain(1)"></image>
		</view>
		<view class="inputs">
			<view class="input">
				<text>{{names}}：</text>
				<input :type="type" class="inpus"  v-model="vals">
			</view>
			<image class="icon" src="../../../static/examine.png" v-show="examine==false" @click="exmain(2)"></image>
			<image class="icon" src="../../../static/examine1.png" v-show="examine==true" @click="exmain(2)"></image>
		</view>
		<button class="btn" @click="determine()">确定</button>
	</view>
</template>

<script>
	const server = require('../../../server');
	const MD5 = require('../../../md5_min');
	export default {
		data() {
			return {
				examine:false,
				examines:false,
				name:'',
				names:'',
				types:'password',
				type:'password',
				password:0,//0 设置密码  1 修改密码
				tan: false, //弹窗
				message: '', //弹窗提示语
				val:'',
				vals:'',
			}
		},
		onLoad() {
			if(uni.getStorageSync('password')!=''){
				this.name = '原密码'
				this.names = '新密码'
				this.password = 1;
			}else{
				this.name = '设置支付密码'
				this.names = '确认支付密码'
				this.password = 0;
			}
		},
		methods: {
			// 提示信息
			prompt(message) {
				let that = this;
				that.tan = true;
				that.message = message;
				setTimeout(function() {
					that.tan = false;
				}, 1100)
			},
			determine(){
				let data ={
					userId:uni.getStorageSync('id')
				};
				let that = this;
				if(this.password==1){
					data.oldPassword = MD5.hex_md5(this.val)
					data.newPassword = MD5.hex_md5(this.vals)
				}else{
					if(this.val!=this.vals){
						this.prompt("密码输入不一致,请重新输入")
						return
					}else{
						data.newPassword = MD5.hex_md5(this.vals)
					}
				}
				server.postJSON('/xinfubao/user/setpassword',data,res=>{
					if(res.data.length!=2){
						this.prompt(res.data[0])
					}else{
						uni.setStorageSync('password',res.data[0].password)
						this.prompt("密码修改成功")
						setTimeout(function() {
							uni.navigateBack({
								delta:1
							})
						}, 1100)
					}
				})
			},
			exmain(id){
				if(id==1){
					this.examines =!this.examines;
					if(this.types =="text"){
						this.types ="password";
					}else{
						this.types ="text";
					}
				}else{
					this.examine =!this.examine;
					if(this.type =="text"){
						this.type ="password";
					}else{
						this.type ="text";
					}
				}
			}
		}
	}
</script>

<style>
.inputs{
	background: white;
	height: 100rpx;
	padding: 0 30rpx;
	box-sizing: border-box;
	display: flex;
	justify-content: space-between;
	align-items: center;
	font-size: 28rpx;
	color: #666666;
	border-top: 1rpx solid #DEDEDE;
}
.inpus{
	color: #333333;
}
.input{
	display: flex;
	align-items: center;
}
.icon{
	width: 32rpx;
	height: 24rpx;
}
</style>
