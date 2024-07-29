<template>
	<view class="body">
		<UserInfo class="user-info"></UserInfo>
		<Content class="content"></Content>
		<!-- <image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view> -->
	</view>
</template>

<script>
	import UserInfo from"../components/UserInfo.vue"
	import Content from "../components/Content.vue"
	export default {
		components:{
			UserInfo,
			Content
		},
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		},
		onLoad(option){
			
		}
	}
</script>

<style scoped>
	.body{
		width: 100%;
		background-color: rgb(241, 241, 243);
	}
	.content {
		width:100%;
		/* display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center; */
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
	
	.user-info{
		width: 100%;
	}
</style>
