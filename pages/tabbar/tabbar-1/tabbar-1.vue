<template>
<view class="top-box">
	
		<view class="top-box-subset">
					
			<image class="img-box1" src="../../../static/img/banjia.png"></image>
		</view>	
			<image class="img-box2" src="../../../static/img/automobile.png"></image>

<view class="box-ioc">
	
		  
 <view class="box-ioc1" @click="gocommodity()" >
		  
		<view class="img-size"> <image  src="../../../static/img/icon_img/house.png" mode=""></image></view>
		  <view class="grid-text"><span>家居</span></view>  
	  </view>
	
		<view class="box-ioc1"  @click="gomap()">
				<view class="img-size"> <image  src="../../../static/img/icon_img/map.png" mode=""></image></view>
				  <view class="grid-text"><span>地图</span></view>  
		</view>
		
		<view class="box-ioc1" @click="goToPage('../../tabbar-3-detial/tabbar-3-release/tabbar-3-release')">
				<view class="img-size"> <image  src="../../../static/img/icon_img/move.png" mode=""></image></view>
				  <view class="grid-text"><span>最新资讯</span></view>  
		</view>
		
		
		<view class="box-ioc1"  @click="gofeedback()">
				<view class="img-size"> <image  src="../../../static/img/icon_img/remain.png" mode=""></image></view>
				  <view class="grid-text"><span>用户反馈</span></view>  
		</view>
		<view class="box-ioc1"   @click="gocommodity()">
				<view class="img-size"> <image  src="../../../static/img/icon_img/salvage.png" mode=""></image></view>
				  <view class="grid-text"><span>废品回收</span></view>  
		</view>
		<view class="box-ioc1" >
				<view class="img-size"  @click.native="gocommodity()"> <image  src="../../../static/img/icon_img/waste.png" mode=""></image></view>
				  <view class="grid-text"><span>回收</span></view>  
		</view>
	
</view>

	<view class="botton-b">	
				<image @click="go()" src="../../../static/img/bddh.png" ></image>
</view>

		</view>	

		
	
</template>

<script>
	
export default {
	
	data() {
		return {
	
		};
	},
	components:{
		

	},
	onLoad() {
		
		
		
	},
	methods: {
		gocommodity(){
	
			    uni.switchTab({
			        url: '../tabbar-2/tabbar-2',
					success: res => {},fail: () => {},complete: () => {}
			    });
		},
		gofeedback(){
			uni.navigateTo({
				url:'../../tabbar-3-detial/tabbar-3-qa/tabbar-3-qa'
			})
		},
		goToPage(url) {
			if (!url) return;
			uni.navigateTo({
				url
			});
		},
	   gomap(){
			uni.switchTab({
			    url: '../tabbar-4/tabbar-4'
			});
		},
		go(){
		 	uni.makePhoneCall({
		 	
		 	// 手机号
		    phoneNumber: '13607959144', 
		
			// 成功回调
			success: (res) => {
				console.log('调用成功!')	
			},
		
			// 失败回调
			fail: (res) => {
				console.log('调用失败!')
			}
			
		  });
		}
		
	}
};
</script>

<style lang="scss">
	// .wrap {
	// 	padding: 40rpx;
	// }
	

	
	.top-box{
		width: 100%;
		height: 100vh;
		background-color: #007AFF;
		z-index: -99;
		
		.top-box-subset{
			width: 100%;
			height: 400rpx;
			background-color: #FFFFFF;
			border-radius: 0 0 50% 0;
			
			.img-box1{
				width: 80%;
				height: 500rpx;
			z-index: 1;	
			}
		}
		
		.img-box2{
	       top: -360rpx;
		   left: 100rpx;
		z-index: 0;	
		margin-top: -300rpx;
		margin-left: 100rpx;
		}
	
	}
	
	
.botton-b{
		position: absolute;
		width: 100%;
		height: 100rpx;
		bottom: 0;
		
		image{
			position: relative;
			width: 40%;
			height: 80rpx;
			margin: 0 30%;
		    bottom: 0;
		}
		
	}

.box-ioc{
			width: 100%;
			height: 400rpx;
			display: flex;
			justify-content: space-around;
			flex-wrap: wrap;
			z-index: 0;
		}


.box-ioc1{
	width: 200rpx;
	height: 100rpx;
	display: flex;
	flex-direction: column;
	margin: 20rpx 0;
	text-align: center;
	z-index: 9999;
	
	.img-size image{
		width: 100rpx;
		height: 100rpx;
		background-color: #FFFFFF;
		box-shadow: 0 0 10rpx #000;
		border-radius: 50%;
		z-index: 9999;
	}
	
	.grid-text span{
		
		font-size: 26rpx;
		color: #FFFFFF;
		z-index: 9999;
	}
	
}

</style>
