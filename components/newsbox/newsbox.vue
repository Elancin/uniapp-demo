<template>
	<view class="newsbox">
		<view class="pic">
			<image :src="item.picurl" mode="aspectFill"></image>
		</view>
		<view class="text">
			<view class="title">
				{{item.title}}
			</view>
			<view class="info" v-if="!item.looktime">
				<text>{{item.author}}</text>
				<text>{{item.hits}}浏览</text>
			</view>
			<view class="info" v-else>
				<text>浏览时间:{{item.looktime}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"newsbox",
		props:{
			item:{
				type:Object,
				default(){
					return{
						title:"默认标题",
						author:"作者",
						hits:666,
						picurl:'../../static/logo.png',
						looktime:'2023-02-06 10:10:20'
					}
				}
			}
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.newsbox{
	display: flex;
	justify-content: space-between;
	.pic{
		width: 230rpx;
		height: 160rpx;
		image{
			width: 100%;
			height: 100%;
		}
	}
	.text{
		flex: 1;
		padding-left: 20rpx;
		.title{
			font-size: 36rpx;
			color: #333;
			overflow:hidden; 
			text-overflow:ellipsis;
			display:-webkit-box; 
			-webkit-box-orient:vertical;
			-webkit-line-clamp:2; 
		}
		.info{
			font-size: 26rpx;
			color: #999;
			text{
				padding-right: 30rpx;
			}
		}
	}
	
}
</style>