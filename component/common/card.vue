<template>
	<!-- 基础卡片组件 -->
	<view class="card" style="width: 100%;">
		<!-- 标题 -->
		<view class="font-md font-weight p-2 border-bottom main-border-color">
			<slot name="title">
				<text class="font-md font-weight">{{headTitle}}</text>
			</slot>
			
		</view>
		<!-- body -->
		<view class="">
			<image v-if="bodyCover" :src="bodyCover" 
			
			mode="widthFix"></image>
			<slot></slot>
		</view>
		
	</view>
</template>

<script>
	export default {
		props:{
			headTitle: String,
			bodyCover: String
		}
	}
</script>

<style>
</style>