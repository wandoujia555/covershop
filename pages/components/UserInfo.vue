<template>
	<view class="info">
		<image class="info-bgc" src="../../static/info-bgc.png" mode=""></image>
		<view class="info-context">
			<view class="img_info">
				<image src="../../static/logo.png" mode=""></image>
			</view>
			<view class="text-info">
				<view class="info-name">
					红包封面商店
				</view>
				<view class="score-info">
					👑 <view class="tag">
						企业店铺
					</view>
				</view>
				<view class="stats-info">
					回头率 {{ "95%" }}    关注数 {{ "263678" }}     所在地: {{ "贵州" }}
				</view>
			</view>
		</view>
		<view class="streamers">
			欢迎光临本店
		</view>
	</view>
</template>
<style scoped>
	
	.info {
		position: relative;
		width: 100%;
		height: 7rem;
		overflow: hidden;
		/* background: url("@/static/background-1.jpg"); */
	}
	.info-context{
		position: relative;
		padding: 0.3rem;
		overflow: hidden;
		width: 100%;
		height: 100%;
		display: flex;
		z-index: 1;
	}
	.info-bgc{
		width: 100%;
		position: absolute;
		left: 0;
		top: 0;
		z-index: 0;
	}
	.img_info {
		width: 4rem;
		height: 4rem;
	}
	.img_info image {
		width: 100%;
		height: 100%;
	}
	
	.text-info{
		padding-left: 0.4rem;
	}
	.info-name{
		font-size: 20px;
		font-weight: 550;
		color: white;
		font-family: "微软雅黑";
	}
	.score-info{
		margin: 2px 0;
		font-size: 12px;
	}
	.tag{
		display: inline-block;
		color: white;
		padding: 2px;
		border-radius: 5px;
		background-color: rgb(41, 124, 230);
	}
	.stats-info{
		color: gray;
		font-size: 12px;
	}
	
	
	/* 横幅 */
	.streamers{
		position: relative;
		padding-top: 0.3rem;
		text-indent: 2em;
		font-size: 12px;
		height: 4rem;
		width: 100%;
		margin-top: -2.2rem;
		background-color: white;
		z-index: 1;
	}
</style>
<script>
	export default {
		name:"UserInfo",
		data() {
			return {
				
			};
		}
	}
</script>

