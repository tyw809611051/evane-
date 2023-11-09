<template>
	<view class="content">
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
		<view class="card" style="width: 100%;">
			<!-- 标题 -->
			<view class="font-md font-weight p-2 border-bottom main-border-color">
				每日精选
			</view>
			<!-- body -->
			<view class="">
				<image src="../../static/images/demo/demo4.jpg" 
				
				mode="widthFix"></image>
			</view>
			
		</view>
	</view>
</template>

<script>
	import swiperImage from "@/component/index/swiper-image.vue";
	import indexNavs from "@/component/index/index-navs.vue";
	import threeAdv from "@/component/index/three-adv.vue"
	export default {
		components:{
			swiperImage,
			indexNavs,
			threeAdv
		},
		data() {
			return {
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
				}

			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	swiper-image,divider,index-navs,three-adv {
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