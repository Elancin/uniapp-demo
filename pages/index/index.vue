<template>
	<view class="home">
		<view class="scrollNav">
			<scroll-view scroll-x class="navScroll" >
				<view class="item " 
				:class="index==navIndex?'active':''" 
				@click='clickNav(index,item.id)' 
				v-for="(item,index) in navArr" :key="item.id">
				{{item.classname}}
				</view>
			</scroll-view>
		</view>
		<view class="content">
			<view class="row" v-for="item in newsArr" :key="item.id">
				<newsbox @click.native="goDetail" :item='item'></newsbox>
			</view>
		</view>
	</view>
</template>

<script >
	export default {
		data() {
			return {
				navIndex:0,
				navArr:[],
				newsArr:[],
			};
		},
		onLoad() {
			this.getNavData()
			this.getNewsData()
		},
		methods:{
			clickNav(index,id){
				this.navIndex=index
				this.getNewsData(id)
			},
			goDetail(){
				uni.navigateTo({
					url:"/pages/detail/detail"
				})
			},
			getNavData(){//获取导航
				uni.request({
					url:"https://ku.qingnian8.com/dataApi/news/navlist.php",
					success:res=>{
						// console.log(res);
						this.navArr=res.data
					}
				})
			},
			getNewsData(id=50){//获取新闻列表
				uni.request({
					url:"https://ku.qingnian8.com/dataApi/news/newslist.php",
					data:{
						num:10,
						cid:id
					},
					success:res=>{
						console.log(res);
						this.newsArr=res.data
					}
				})
			}
		}
	}
</script>

<style scoped lang="scss">
.navScroll{
	height: 100rpx;
	background-color: #F7F8FA;
	white-space: nowrap;
	position: fixed;
	top:let(--window-top);
	left: 0;
	z-index: 10;
	.item{
		font-size: 40rpx;
		display: inline-block;
		line-height: 100rpx;
		padding: 0 30rpx;
		&.active{
			color: #31c27c;
		}
	}
}
.content{
	padding: 30rpx;
	padding-top: 100rpx;
	.row{
		border-bottom: 1px dashed #efefef;
		padding: 20rpx 0;
	}
}
</style>
