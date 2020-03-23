<template>
	<view class="backgrounds">
		<view class="head_tab">
			<view class="heads_tab">
				<view :class="tab==0?'active':''" @click="tab=0">聚焦疫情</view>
				<view :class="tab==1?'active':''" @click="tab=1">捐助榜单</view>
			</view>
		</view>
		<view class="content">
			<view class="swiper">
				<view class="swiper_list">
					<view>90**抽中了20紫薇币</view>
					<view>刚刚</view>
				</view>
				<view class="swiper_list">
					<view>90**抽中了20紫薇币</view>
					<view>刚刚</view>
				</view>
			</view>
		</view>
		<view class="contents" v-show="tab==0">
				<image src="../../../../static/1.png" class="image"></image>
				<view class="font">
					常孝股份·中华孝道园，十九年勤勉耕耘，致力于孝道事业和幸福产业的建设，旨在通过孝道信仰结合实体经济打造幸福产业生态。中华孝道园是国家4A景区，拥有860亩太湖大美山水园林，更拥有江南第一家百家姓祠堂、全国唯一三世观音圣境。一直以来祈福祭祖，连根养根，祭祀天地，福佑中华！
				</view>
				<view class="fonts">
					从2019年12月初，疫，就悄悄藏在武汉的街头巷陌，不知不觉地，新冠肺炎在全国范围内蔓延、扩散开。随着国家各级政府和医院对疫情的正视，举国上下都意识到，我们是在同一个狡猾的魔鬼战斗。防疫工作开展以来，多少人坚守奋战，多少次祈祷期盼。虽然我们哪里都不能去，但我们每个人都默默坚守着，期待疫情之后的幸福生活。为了表达对疫情发生以来一直奋战在一线的医护人员的敬意，常孝股份·中华孝道园率先行动：自景区恢复运营之日至2020年12月31日期间，中华孝道园将对全国范围内所有医护人员实行免费开放政策！届时医护人员凭有效证件（医师证或护士证）即可免费入园！				
				</view>
				<image src="../../../../static/2.png" class="images"></image>
				<view class="fonts">
					常州孝道文化产业股份有限公司（以下简称“常孝股份”）专注于幸福产业，以孝文化为魂，以康养、旅游，文化创意产业为业态载体，大力发展“家”文化产业。公司秉持“传承、感恩、标杆、奉献”的核心价值观，以“机制创新、产品创新、模式创新”为发展理念，运用区块链思维与技术将自身的实物资产数字通证化，以版通等不同形式实施消费、投资与应用，满足会员的不同需求。
				</view>
				<image src="../../../../static/3.png" class="imagess"></image>
				<image src="../../../../static/4.png" class="imagess"></image>
				<image src="../../../../static/5.png" class="imagess"></image>
				<image src="../../../../static/6.png" class="imagess"></image>
				<image src="../../../../static/7.png" class="imagesss"></image>
				<view class="fonts">
					常孝股份·中华孝道园是以中华传统文化精髓——孝道文化为核心的国家AAAA级文化景区。园区坐落于太湖之滨的武进太湖湾旅游度假区内，景区占地面积860亩，面朝太湖，背倚蓼莪山脉，山水相依，风景秀美，拥有丰富的历史、文化、旅游资源，是江南一带的“世外桃源”。自2002年历时10年规划建设，2012年正式开园，广迎天下孝子贤孙，有识之士。中华孝道园汲取中国传统儒释道文化中的孝道核心，以全方位的视角，深入的孝道体验，让天下中华儿女感悟孝道，传承孝道，践行孝道！
				</view>
				<image src="../../../../static/8.png" class="imagess"></image>
				<image src="../../../../static/9.png" class="imagess"></image>
				<image src="../../../../static/10.png" class="imagess"></image>
				<image src="../../../../static/11.png" class="imagess"></image>
				<view class="fonts">
					时值中华逢此疫情危难时刻，在配合国家抗疫防疫的战略同时，不忘初心，共同祈福护佑我中华民族顺利度过危难。同时也用自己的微薄之力，向战斗在一线的工作人员，送上真诚的祝福。除了推出了医护工作者全年免费入园的政策之外。我们还推动“您祈福 我捐赠”的祈福捐赠活动。
				</view>
			</view>
		<view v-show="tab==1">
			<view class="list_content"> 
				<view class="list_icon">
					<image class="list_content_img" src="../../../../static/gold.png"></image>
					<view class="userinfor">
						<view class="name">小贝哈哈</view>
						<view class="time">2019-12-01</view>
					</view>
				</view>
				<view>10000积分</view>
			</view>
			<view class="list_content">
				<view class="list_icon">
					<image class="list_content_img" src="../../../../static/silver.png"></image>
					<view class="userinfor">
						<view class="name">小贝哈哈</view>
						<view class="time">2019-12-01</view>
					</view>
				</view>
				<view>10000积分</view>
			</view>
			<view class="list_content">
				<view class="list_icon">
					<image class="list_content_img" src="../../../../static/copper.png"></image>
					<view class="userinfor">
						<view class="name">小贝哈哈</view>
						<view class="time">2019-12-01</view>
					</view>
				</view>
				<view>10000积分</view>
			</view>
		</view>
		<view class="bottom_btn">
			<view class="bottom_btns">
				<button class="btns" @click="donation">我要捐款</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tab:0,//顶部tab  0 聚焦疫情   1 捐助榜单
			}
		},
		methods: {
			donation(){
				uni.navigateTo({
					url:'donation/donation'
				})
			}
		}
	}
</script>

<style>
.head_tab{
	position: relative;
	width: 100%;
	height: 88rpx;
	
}
.heads_tab{
	z-index: 55;
	position: fixed;
	background: white;
	display: flex;
	justify-content: space-around;
	align-items: center;
	width: 100%;
	height: 88rpx;
	color: #999999;
	font-size: 28rpx;
}
.heads_tab view{
	height: 88rpx;
	width: 120rpx;
	line-height: 88rpx;
	text-align: center;
}
.active{
	color: #161616;
	border-bottom: 2px solid #DE342F;
}
.content{
	padding:20rpx 32rpx;
	box-sizing: border-box;
}
.swiper{
	width: 100%;
	height: 132rpx;
	background: white;
	padding: 24rpx;
	box-sizing: border-box;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	border-radius: 10rpx;
	font-size: 24rpx;
}
.swiper_list{
	display: flex;
	justify-content: space-between;
}
.bottom_btn{
	position: relative;
	width: 100%;
	height: 128rpx;
}
.bottom_btns{
	position: fixed;
	width: 100%;
	height: 128rpx;
	display: flex;
	align-items: center;
	justify-content: center;
	background: white;
	bottom: 0;
}
.btns{
	background: #DD0812;
	width: 686rpx;
	height: 88rpx;
	text-align: center;
	line-height: 88rpx;
	color: #FFFFFF;
	font-size: 32rpx;
}
.contents{
	display: flex;
	flex-direction: column;
	padding:0 32rpx;
	box-sizing: border-box;
	background: #FAFAFA;
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
.list_content{
	width: 100%;
	height: 132rpx;
	border-bottom: 1rpx solid #FAFAFA;
	display: flex;
	padding:0 30rpx;
	box-sizing: border-box;
	align-items: center;
	font-size: 30rpx;
	color: #333333;
	justify-content: space-between;
	background: white;
}
.list_content_img{
	width: 60rpx;
	height: 60rpx;
	margin-right: 30rpx;
}
.list_icon{
	display: flex;
	align-items: center;
}
.userinfor{
	display: flex;
	flex-direction: column;
}
.time{
	margin-top: 16rpx;
	font-size: 24rpx;
	color: #999999;
}
</style>
