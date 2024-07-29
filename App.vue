<script>
	import config from "./config.js"
	uni.login({
		success(res) {
			console.log(res.code)
			uni.request({
				url:"http://"+config.server.address+"/login",
				data:{
					code:res.code
				},
				success({data}){
					uni.setStorageSync('openid',data)
					console.log(data)
				}
			})
		}
	})
	
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
</style>
