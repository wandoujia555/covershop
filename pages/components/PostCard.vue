<template>
	<view class="postcard">
		<view class="postcard-top">
			<view class="user-img">
				<image src="../../static/logo.png" mode=""></image>
			</view>
			<view class="wclink">
				进店
			</view>
			<view class="user-name">
				红包封面商店
			</view>
			<view class="score">
				👑
			</view>
			
		</view>
		<view class="postcard-vottom">
			<label><view class="online">·</view>55分钟前登录</label>
			<label>13.8万人关注</label>
			<label>95%回头率</label>
			<label>24小时内发货</label>
		</view>
	</view>
</template>

<script>
</script>

<style scoped>
	.postcard{
		width: 100%;
		background-color: white;
	}
	.user-img{
		float: left;
		/* display: inline-block; */
		width: 2rem;
		height: 2rem;
	}
	.user-img image{
		width: 100%;
		height: 100%;
	}
	.user-name {
		display: inline-block;
	}
	.wclink{
		margin-right: 10px;
		padding:0.4rem 1rem;
		font-size: 12px;
		border-radius: 6px;
		float: right;
		color: white;
		background-color: red;
	}
	.postcard-vottom{
		position: relative;
		/* overflow: hidden; */
	}
	.postcard-vottom label {
		font-size: 8px;
		margin:  0 0.8rem;
	}
	.online {
		bottom: 4px;
		left: -6px;
		
		position: absolute;
		display: inline-block;
		font-family: 'Courier New', Courier, monospace;
		line-height: 0px;
		/* font-weight: 800; */
		font-size: 40px; 
		color: green;
	}
</style>