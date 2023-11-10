<template>
	<view class="" style="width: 372.5upx;">
		<image :src="resdata.cover" 
		lazy-load
		mode="widthFix"></image>
		<view class="p-2 pt-1">
			<view class="font-md">{{resdata.title}}</view>
			<view class="text-light-muted">{{resdata.desc}}</view>
			<view class="d-flex my-1">
				<price :price="resdata.price"></price>
				<view class="line-h font-sm text-light-muted line-through ml-1 a-self-end" >¥{{resdata.oprice}}</view>
			</view>
		</view>
	</view>
</template>

<script>
	import price from "@/component/common/price.vue"
	
	export default {
		components:{
			price
		},
		props:{
			resdata:Object
		}
	}
</script>

<style>
</style>