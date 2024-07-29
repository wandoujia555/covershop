<template>
	<view class="body">
		<view class="bar-top">
			<view class="bar-connet">
				<li>全部</li>
				<li>待付款</li>
				<li @click="changeSelect(2)">已付款</li>
				<!-- <li>查询订单</li> -->
			</view>
		</view>
		<view class="content">
			<ul class="orders-ul" v-if="orders.length!=0">
				<li v-for="item of orders" class="orders-li">
					<view class="li-top">
						<view class="li-left">
							<view class="name">
								{{ item.name }}
							</view>
							
							<view class="cover_png">
								<image :src="link" mode=""></image>
							</view>
						</view>
						<view class="li-right">
							<view class="query" @click="toOrder(item.oid)">
								查询序列号
							</view>
							<view class="amount">
								￥{{ item.amount*0.01 }}
								<br>
								×1
							</view>
						</view>
					</view>
					<view class="connet">
						订单号: {{ item.oid }}
					</view>
				</li>
			</ul>
			<view v-else>
				<view class="bg">
					<image src="../../static/nocover-bg.png" mode=""></image>
					<view class="text">
						暂无商品分类
					</view>
				</view>
			</view>	
		</view>
	</view>
</template>

<script>
	import coverlink from "../../static/coverlink.json"
	import config from "../../config.js"
	export default {
		data() {
			return {
				select:0,
				orders:[],
				link:""
			}
		},
		methods: {
			changeSelect(){
				var that = this
				this.select = 2;
				uni.request({
					url:`http://${config.server.address}/getOrder`,
					data:{
						openid:uni.getStorageSync('openid')
					},
					success:({data})=>{
						console.log(data)
						that.orders=data
					}
				})
				this.link = coverlink.cover[0].cover
				console.log(coverlink.cover[0].cover)
			},
			toOrder(oid){
				uni.navigateTo({
					url:`../orders_connet/orders_connet?oid=${oid}`
				});
			}
		},
		onLoad(){
			this.changeSelect(2)
		}
	}
</script>

<style scoped>
	.body{
		min-height: 100vh;
		background-color: rgb(243, 245, 246);
	}
	.bar-top{
		height: 2rem;
		padding: 0.2rem 0;
		background-color: white;
		margin-bottom: 20px;
		
	}
	.bar-connet{
		display: flex;
		justify-content: center;
	}
	.bar-connet view{
		color: gray;
		line-height: 2rem;
		flex: 1;
		text-align: center;
	}
	.bg{
		margin: auto;
		width: 100px;
		height: 50px;
	}
	.bg image{
		height: 100%;
		width: 100%;
	}
	.text{
		color: gray;
	}
	
	
	
	.orders-li{
		display: flex;
		flex-direction:column;
		border-radius: 6px;
		background-color:white;
		margin: 0 20px;
		margin-bottom: 16px;
		padding: 4px;
	}
	.connet{
		font-size: 12px;
	}
	
	.query{
		font-size: 14px;
		float: right;
		background-color: orangered;
		border-radius: 6px;
		/* margin-top: 0px; */
		padding: 4px;
		
	}
	
	.amount{
		/* color: gray; */
		text-align: right;
		margin-top: 40px;
		/* float: right; */
	}
	.cover_png {
		width: 100px;
		height: 100px;
	}
	.cover_png image{
		width: 100%;
		height: 100%;
	}
	.li-top{
		display: flex;
	}
	.li-left{
		flex: 1;
	}
	.li-right {
		padding-top: 10px;
		flex: auto;
	}
</style>
