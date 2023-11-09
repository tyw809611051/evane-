<template>
	<view class="">
		<!-- 首页分类 -->
		<view class="row w-100 j-center m-2">
			<block v-for="(item,index) in resdata" :key="index">
				<view class="span-4 j-center a-center d-flex flex-column py-2">
					<image :src="item.src"
					 style="width: 60upx;height: 60upx;"
					 mode="widthFix"></image>
					 <text class="font-sm">{{item.text}}</text>
				</view>
			</block>
		</view>
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