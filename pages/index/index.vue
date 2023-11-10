<template>
	<view class="content">
		<!-- 顶部选项卡 -->
		<scroll-view scroll-x class="scroll-row border-bottom" style="height: 80rpx;" :scroll-into-view="scrollinto" :scroll-with-animation="true">
			<view v-for="(item,index) in tabBars" :key="index" class="scroll-row-item px-3"
			@tap="changeTab(index)"
			:class="tabIndex === index ? 'main-text-color':''" 
			:id="'tab'+index"
			style="height: 80rpx;line-height: 80rpx;">
				<text class="font-md">{{item.name}}</text> 
			</view>
		</scroll-view>
		
		<swiper :current="tabIndex" :style="'height:'+srollH+'px;width:100%;'" @change="onChangeTab">
			<swiper-item v-for="(item,index) in tabBars" :key="index">
				<scroll-view scroll-y="true" :style="'height:'+srollH+'px;'">
					
					<!-- 轮播图组件 -->
					<swiper-image :resdata="swipers"></swiper-image>
					
					<!-- 首页分类 -->
					<index-navs :resdata="indexnavs"></index-navs>
					
					<!-- 分割线 -->
					<divider></divider>
					
					<!-- 三图广告 -->
					<three-adv :resdata="threeAdv"></three-adv>
					
					<!-- 分割线 -->
					<divider></divider>
					
					<!-- 基础卡片组件 -->
					<card headTitle="每日精选" bodyCover="/static/images/demo/demo4.jpg"/>
				
					<!-- 公告列表组件 -->
					<view class="row j-sb w-100">
						<block v-for="(item2,index2) in commonList" :key="index2">
							<commonList :resdata="item2"></commonList>
						</block>
					</view>
				</scroll-view>
			</swiper-item>
		</swiper>

	</view>
</template>

<script>
	import swiperImage from "@/component/index/swiper-image.vue";
	import indexNavs from "@/component/index/index-navs.vue";
	import threeAdv from "@/component/index/three-adv.vue"
	import card from "@/component/common/card.vue"
	import commonList from "@/component/common/common-list.vue"
	export default {
		components:{
			swiperImage,
			indexNavs,
			threeAdv,
			card,
			commonList
		},
		data() {
			return {
				scrollinto:"tab1",
				srollH:500,
				tabIndex:0,
				tabBars:[
					{
						name:"推荐"
					},
					{
						name:"关注"
					},
					{
						name:"体育"
					},
					{
						name:"推荐"
					},
					{
						name:"关注"
					},
					{
						name:"体育"
					},
					{
						name:"推荐"
					},
					{
						name:"关注"
					},
					{
						name:"体育"
					}
				],
				swipers: [{
						src: "../../static/images/bg.jpg"
					},
					{
						src: "../../static/images/bg.jpg"
					},
					{
						src: "../../static/images/bg.jpg"
					}
				],
				indexnavs:[
					{src:"../../static/images/indexnav/1.png",text:"新品发布3"},
					{src:"../../static/images/indexnav/1.png",text:"新品发布"},
					{src:"../../static/images/indexnav/1.png",text:"新品发布"},
					{src:"../../static/images/indexnav/1.png",text:"新品发布"},
					{src:"../../static/images/indexnav/1.png",text:"新品发布2"},
					{src:"../../static/images/indexnav/1.png",text:"新品发布3"},
					{src:"../../static/images/indexnav/1.png",text:"新品发布"},
					{src:"../../static/images/indexnav/1.png",text:"新品发布"},
					{src:"../../static/images/indexnav/1.png",text:"新品发布"},
					{src:"../../static/images/indexnav/1.png",text:"新品发布2"}
				],
				threeAdv:{
					big: {
						src:"../../static/images/demo/demo1.jpg"
					},
					smalltop:{
						src:"../../static/images/demo/demo2.jpg"
					},
					smallbottom:{
						src:"../../static/images/demo/demo3.jpg"
					}
				},
				commonList:[
					{
						cover:"/static/images/demo/list/1.jpg",
						title:"米家空调",
						desc:"1.5匹变频",
						oprice:"2699",
						price:1532
					},
					{
						cover:"/static/images/demo/list/2.jpg",
						title:"米家空调",
						desc:"2.5匹变频",
						oprice:"2699",
						price:1632
					},
				]

			}
		},
		onLoad() {
			// 获取可视区高度
			uni.getSystemInfo({
				success: (res) => {
					this.srollH = res.windowHeight - uni.upx2px(80)
				}
			})
		},
		methods: {
			// 切换选项卡
			changeTab(index){
				if (this.tabIndex == index) {
					return;
				}
				this.tabIndex = index;
				this.scrollinto= 'tab'+index;
			},
			// 监听滑动列表
			onChangeTab(e) {
				this.changeTab(e.detail.current)
			}
		}
	}
</script>

<style>
	swiper-image,divider,index-navs,three-adv,card {
		width: 100%;
	}
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>