
<template>
	<view class="body">
		<video class="video" :src="videosrc"></video>
		<view class="detailCardFirst">
			<view class="sales">
				销量{{ sales }}
			</view>
			<view class="price">
				售价:{{ price }}
			</view>
			<view class="title">
				爆款 城堡
			</view>
			
		</view>
		<view class="detailCardSecond">
			<view class="guaranteeSection">
				保证金保障   交易资金担保
			</view>
		</view>
		<PostCard></PostCard>
		<view class="detailCardThird">
			<view class="detailCardThird-text">
				商品详情
			</view>
			<image src="https://img.alicdn.com/imgextra/i1/2215065227322/O1CN01H74qCI23xWuULywPd_!!2215065227322.png" mode=""></image>
		</view>
		<view class="detailCardForth">
			<view class="detailCardThird-text">
				购前说明
			</view>
			<image src="../../static/d-bgc.webp" mode=""></image>
		</view>
		<view class="barBottom">
			<view class="home">
				<image src="" mode=""></image>
				<label>
					店铺
				</label>
			</view>
			<view class="customer">
				<image src="" mode=""></image>
				<label class="">
					联系商家
				</label>
			</view>
			<view class="buy">
				<view class="buy-text" @click="pay">
					立即购买
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	import config from "../../config.js"
	import PostCard from "../components/PostCard.vue"
	export default {
		components:{
			PostCard
		},
		data() {
			return {
				sales:'',
				price:'',
				id:"",
				videosrc:''
			}
		},
		methods: {
			getsrcById(){
				return "视频1.mp4"
			},
			payment(data){
				
			},
			pay(){
				
				uni.request({
					url:`http://${config.server.address}/prepay`,
					data:{
						// name:"红包2",
						name:"[抖音爆款]闪耀金色城堡",
						openid:uni.getStorageSync('openid')
					},
					success({data}){
						console.log(data)
						console.log(data.paySign)
						wx.requestPayment({
							timeStamp:data.timeStamp,
							nonceStr: data.nonceStr,
							package: data.package,
							signType: data.signType,
							paySign: data.paySign,
							success(res) {console.log(res)},
							fail(e) {console.log(e)}
						})
					}
				})
				
			},
			
		},
		
		onLoad(options){
			uni.request({
				url:`http://gw.api.agiso.com/acpr/CardPwd/HandPick`,
				data:{
					cpkId:934294,
					num:1,
					handPickOrderId:"100000",
					buyer:"豌豆荚",
					buildCpd:true
				},
				success(res){
					console.log((res))
				}
			})
			
			
		    // let userInfo = JSON.parse(decodeURIComponent(options.info));
			this.sales = "5.5万"
			this.price = "10.88"
			this.id = options.id
			this.videosrc = "http://"+config.server.address+"/video/"+this.id
		    console.log(options.id);
		}
	}
</script>

<style scoped>
	.body{
		background-color:rgb(241, 241, 243) ;
	}
	.body view{
		background-color: white;
	}
.video{
	width: 100%;
}
.detailCardFirst{
	background-color: #FFF;
}
.title{
	font-size: 14px;
	/* color: white; */
}
.title{
	
}
.sales{
	font-size: 12px;
	float: right;
}

	
.detailCardSecond{
	padding: 10px;
	margin:6px 0;
	font-size: 12px;
	background-color: #FFF;
}


.aaa{
	height: 20px;
	width: 20px;
	background: #123;
}



.detailCardThird-text{
	margin-top: 10px;
	padding: 4px;
	border-bottom: 1px solid rgb(241, 241, 243);
}
.detailCardThird image{
	width: 100%;
}
.detailCardThird-text {
	padding: 4px;
	border-bottom: 1px solid rgb(241, 241, 243);
}
.detailCardForth image{
	width: 100%;
	height: 1000px;
}

.barBottom{
	height: 4rem;
	position: sticky;
	bottom: 0px;
	box-shadow: 0px -4px 10px rgba(0, 0, 0, 0.1);
	background-color: white;
}
.barBottom view{
	margin:0 0.2rem;
}
.home {
	float: left;
	
}
.home image {
	width: 100%;
	height: 100%;
}
.customer {
	float: left;
}
.customer image{
	display: inline-block;
	width: 100%;
	height: 100%;
}
.buy{
	width: 100px;
	position: relative;
	height: 100%;
	float: right;
}
.buy .buy-text{
	color: white;
	padding:0 10px;
	height: 40px;
	position: absolute;
	top: calc(50% - 20px);
	line-height: 40px;
	background-color: red;
	border-radius: 5px;
}
</style>
