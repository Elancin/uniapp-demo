<template>
	<view class="user">
		<view class="top">
			<image src="../../static/icon/时间.svg" mode=""></image>
			<text>浏览历史</text>
		</view>
		<view class="content">
			<view class="row" v-for="(item,index) in 10" key="index">
				<newsbox @click.native="goDetail"></newsbox>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods:{
			goDetail(){
				uni.navigateTo({
					url:"/pages/detail/detail"
				})
			}
		}
	}
</script>

<style lang="scss">
.user{
	.top{
		padding: 50rpx 0;
		background-color: #f8f8f8;
		color: #666;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		image{
			width: 150rpx;
			height: 150rpx;
		}
		.text{
			font-size: 36rpx;
			padding-top: 20rpx;
		}
	}
	.content{
		padding: 30rpx;
		.row{
			border-bottom: 1px dashed #efefef;
			padding: 20rpx 0;
		}
	}
}
</style>
