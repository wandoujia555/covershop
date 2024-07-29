<template>
	<view class="classify">
		<view class="search-box">
			<view class="search">
				<view class="search-text">
					搜索
				</view>
			</view>
		</view>
		<view class="bg">
			<image src="../../static/nocover-bg.png" mode=""></image>
			<view class="text">
				暂无商品分类
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
	.classify{
		min-height: 100vh;
		height: 100%;
		width: 100%;
		background-color: rgb(243, 245, 246);
	}
	.search-box{
		background-color: white;
		height: 2rem;
		margin: 10px 0;
	}
	.search{
		text-align: center;
		background-color: rgb(235, 235, 236);
	}
	.search-text{
		color: gray;
/* 		width: 40px; */
		display: inline-block;
		margin: auto;
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
</style>
