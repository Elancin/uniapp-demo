<template>
	<view class="detail">
		<view class="title">标题</view>
		<view class="info">
			<view class="author">编辑</view>
			<view class="time">2023</view>
		</view>
		<view class="content">内容</view>
		<view class="description">声明</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.detail{
		padding: 30rpx;
		.title{
			font-size: 46rpx;
			color: #333;
		}
		.info{
			background-color: #f6f6f6;
			padding: 20rpx 10rpx;
			font-size: 25rpx;
			color: #666;
			display: flex;
			justify-content: space-between;
			margin: 40rpx 0;
		}
		.content{
			padding-bottom: 50rpx;
		}
		.description{
			background-color: #fef0f0;
			font-size: 26rpx;
			padding: 20rpx;
			color: #f89898;
			line-height: 1.8em;
		}
	}
</style>
