<template>
	<view>
		<view class="top">
			红包序列号{{key}}
		</view>
		<view class="copy">
			复制
		</view>
		<view class="enter">
			兑换入口
		</view>
		
		<view class="">
			注意事项:<br>
			1.切勿告诉他人<br>
			2.一定在确定口令可用后再确认收获，以免发生纠纷
		</view>
	</view>
</template>

<script>
	import config from "../../config.js"
	export default {
		data() {
			return {
				key:""
			}
		},
		methods: {
			
		},
		onLoad(options){
			var that = this;
			uni.request({
				url:`http://${config.server.address}/query/${options.oid}`,
				data:{
					openid:uni.getStorageSync('openid')
				},
				success:({data})=>{
					if( data.key){
						that.key = data.key
					}else if(data == "货源空"){
						that.key = "货源空,请联系退货"
					}else if(data == "支付未完成"){
						that.key = "支付未完成"
					}else{
						that.key = "订单错误"
					}
					console.log(data)
				}
			})
		    console.log(options);
		}
	}
</script>

<style>

</style>
