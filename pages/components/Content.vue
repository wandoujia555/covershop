<template>
	<view class="box">
		<view class="title">
			<image src="../../static/selected-tabbar/menu-fire.png" mode=""></image>
			<view class="title-text">
				热门红包
			</view>
		</view>
		<view class="content">
			
			<view class="cover-box" v-for="item in covers">
				<RedCover class="cover" :list="item" ></RedCover>
			</view>
			<!-- <RedCover class="cover"></RedCover>
			<RedCover class="cover"></RedCover>
			<RedCover class="cover"></RedCover>
			<RedCover class="cover"></RedCover> -->
		</view>
	</view>
</template>


<script>
	import coverlink from "../../static/coverlink.json"
	import RedCover from "./RedCover.vue"
	//coverlink.cover
	export default {
		components:{
			
			RedCover
		},
		data() {
			return {
				covers:["aaa","bbb"],
				title: 'Hello'
			}
		},
		created() {
			// console.log(coverlink.cover)
			this.covers = coverlink.cover
			// console.log(this.covers)
		},
		methods: {
	
		}
	}
</script>

<style scoped>
	.box{
		position: relative;
	}
	.content{
		width: 100%;
		display: grid;
		grid-template-columns: repeat(2, 50%);
		/* grid-template-columns: 1fr 50%; */
		/* grid-template-rows: repeat(2, 40%); */
	}
	.title{
		height: 20px;
		color: gray;
		left: 2px;
		top: 5px;
		position: absolute;
	}
	.title-text{
		display: inline-block;
		position: absolute;
		left: 16px;
		top: 0;
		height: 20px;
		width: 160px;
		line-height: 20px;
	}
	.title image{
		position: absolute;
		left: 2px;
		top: 3px;
		width: 14px;
		height: 14px;
	}
	.cover-box {
		margin: 8px 5px;
		height: 260px;
	}
	.content .cover{
		margin:0 20px;
		width: calc(100%-20px);
		flex:1;
	}
</style>