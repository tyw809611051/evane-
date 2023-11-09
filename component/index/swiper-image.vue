<template>
	<view class="">
		<swiper :autoplay="true" :interval="3000" :duration="1000" circular>
			<block v-for="(item,index) in resdata" :key="index">
				<swiper-item>
					<view class="swiper-item">
						<image :src="item.src" lazy-load style="height: 350upx;" mode=""></image>
					</view>
				</swiper-item>
			</block>
		</swiper>
	</view>
</template>

<script>
	export default {
			props:{
				resdata:Array
			}
		}
</script>

<style>
</style>