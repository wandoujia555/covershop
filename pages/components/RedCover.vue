<template>
	<view class="cover-shop" @click="aaa">
		<view class="cover-img">
			<!-- <image src="../../static/cover1.png" alt="" /> -->
			<image :src="coverimgurl" alt="" />
		</view>
		<view class="cover-info">
			<view class="cover-name">
				{{ list.name }}
			</view>
			<view class="cover-price">
				<label class="cover-price-int">￥{{ priceInt }}</label>.{{ priceF }}
			</view>
			<view class="sales">
				销量:{{ list.sales }}
			</view>
		</view>
		<view class="shop-cart">
			<image src="../../static/icon/gouwuche.svg" mode=""></image>
		</view>
	</view>
</template>

<script>
	export default {
		props: ['list'],
		data() {
			return {
				coverimgurl:"",
				title: 'Hello',
				name:"",
				priceInt:"",
				priceF:""
			}
		},
		created() {
			this.coverimgurl = this.list.cover;
			let price = this.list.price.split(".")
			this.priceInt = price[0]
			this.priceF = price[1]
			
		},
		methods: {
			aaa:()=>{
				uni.navigateTo({
					url:`../CoverDetail/CoverDetail?id=${1}`
				});
			}
		}
	}
	
</script>

<style>
	.shop-cart{
		position:absolute;
		right:6px;
		bottom: 8px;
	}
	.shop-cart image {
		/* position: absolute; */
		height: 2em;
		width: 2em;
	}
	.cover-shop{
		position: relative;
		width: 100%;
		height:260px;
		overflow: hidden;
		background-color: #fff;
		border-radius:6px;		
	}
	.cover-img{
		width: 100%;
	}
	.cover-img image{
		width: 100%;
		height:170px;
	}
	
	.cover-info{
		font-weight: 1000;
		font-size: 10px;
	}
	
	.cover-name{
		height: 3em;
		color: rgb(53, 53, 53);
		font-family: "微软雅黑";
		font-size: 12px;
		/* font-weight: 200px; */
	}
	.cover-price{
		color: red;
		font-size: 12px;
		margin: 2px 0;
	}
	.cover-price-int{
		margin-left: 2px;
		font-size: 18px;
		display: inline-block;
	}
	.sales {
		margin-left: 2px;
		margin-top: 6px ;
		color: gray;
	}
</style>