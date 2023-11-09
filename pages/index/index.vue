<template>
	<view class="content">
		<!-- 轮播图组件 -->
		<swiper-image :resdata="swipers" style="width: 100%;"></swiper-image>
		
		<!-- 首页分类 -->
		<view class="row w-100 j-center m-2">
			<view class="span-4 j-center a-center d-flex flex-column py-2">
				<image src="../../static/images/indexnav/1.png"
				 style="width: 60upx;height: 60upx;"
				 mode="widthFix"></image>
				 <text class="font-sm">新品发布</text>
			</view>
			<view class="span-4 j-center a-center d-flex flex-column py-2">
				<image src="../../static/images/indexnav/1.png"
				 style="width: 60upx;height: 60upx;"
				 mode="widthFix"></image>
				 <text class="font-sm">新品发布</text>
			</view>
			<view class="span-4 j-center a-center d-flex flex-column py-2">
				<image src="../../static/images/indexnav/1.png"
				 style="width: 60upx;height: 60upx;"
				 mode="widthFix"></image>
				 <text class="font-sm">新品发布</text>
			</view>
			<view class="span-4 j-center a-center d-flex flex-column py-2">
				<image src="../../static/images/indexnav/1.png"
				 style="width: 60upx;height: 60upx;"
				 mode="widthFix"></image>
				 <text class="font-sm">新品发布</text>
			</view>
			<view class="span-4 j-center a-center d-flex flex-column py-2">
				<image src="../../static/images/indexnav/1.png"
				 style="width: 60upx;height: 60upx;"
				 mode="widthFix"></image>
				 <text class="font-sm">新品发布</text>
			</view>
		</view>
	</view>
</template>

<script>
	import swiperImage from "@/component/index/swiper-image.vue";
	export default {
		components:{
			swiperImage
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
				]

			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
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