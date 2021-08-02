<template>
	<view class="content">
		<view>
			<view class="top">
				<view class="center">
					<view class="center_top">
						<view class="center_img" @tap="toBaseInfo">
							<image :src="yonghuwx.avatarUrl"></image>

							<open-data type="userAvatarUrl" class="user_head"></open-data>
						</view>
						<view class="center_info" @tap="toBaseInfo">
							<view class="center_name">{{ yonghuwx.nickName }}</view>

							<!-- <view class="center_phone">phone:{{phone}}</view> -->
							<view class="center_phone">基本信息</view>
						</view>
					</view>
					<view class="center_down">
						<view class="center_rank" @tap="toNone">
							<image class="rank_icon" src="../../../static/jc.png"></image>
							<text class="rank_text">我的排名</text>
						</view>
						<view class="center_score" @tap="toNone">
							<image class="rank_icon" src="../../../static/jf.png"></image>
							<text class="rank_text">我的积分</text>
						</view>
					</view>
				</view>
				<image
					src="https://6661-fatdown-wxapp-sg2p1-1300398887.tcb.qcloud.la/wave.gif?sign=045605c672f482a8c3d428abed669aa7&t=1570674356"
					mode="scaleToFill"
					class="gif-wave"
				></image>
			</view>
		</view>
		<view class="box-cord">
			<view class="cord1">
				<image src="../../../static/imgs/gold.png" mode=""></image>
				<span>积分</span>
			</view>

			<view class="cord1">
				<image src="../../../static/imgs/integral.png" mode=""></image>
				<span>商城</span>
			</view>

			<view class="cord1" @click="getphone">
				<image src="../../../static/imgs/phone.png" mode=""></image>
				<span>电话号码</span>
				<u-action-sheet  :border-radius=20 :list="list" @click="click" v-model="show"></u-action-sheet>
			</view>
		</view>

		<view class="list-call">
			<u-cell-group>
				<u-cell-item icon="car" title="我的订单" :arrow="true" arrow-direction="right"></u-cell-item>
				<u-cell-item icon="phone-fill" title="电话资讯" :arrow="true" arrow-direction="right"></u-cell-item>
				<u-cell-item icon="chat" title="用户反馈" :arrow="true" arrow-direction="right"></u-cell-item>
				<u-cell-item icon="server-man" title="询问客服" :arrow="true" arrow-direction="right"></u-cell-item>
			</u-cell-group>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			title: 'Hello',
			src: 'http://pic2.sc.chinaz.com/Files/pic/pic9/202002/hpic2119_s.jpg',
			text: '无头像',
			yonghuwx: [],
				list: [{
								text: '联系电话:13607959144',
								color: '#282C35'
							
							}, {
								text: '联系电话:18107953232'
							}],
							show: false
		};
	},
	onLoad() {
		let that = this;
		uni.login({
			provider: 'weixin',
			success: function(loginRes) {
				// 获取用户信息
				uni.getUserInfo({
					provider: 'weixin',
					success: function(infoRes) {
						that.yonghuwx = infoRes.userInfo;
						console.log(that.yonghuwx);
					}
				});
			}
		});
	},
	methods: {
		getphone(){
			let that = this;
			that.show = true
			
		},
		
	click(index) {
		console.log(`点击了第${index + 1}项，内容为：${this.list[index].text}`)
		if(index == 0){
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
		}else if(index == 1){
			
			uni.makePhoneCall({
					 	
					 	// 手机号
			  phoneNumber: '18107953232', 
					
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
		
	}
};
</script>

<style lang="scss">
Page {
	font-size: 28rpx;
}

.top {
	width: 100%;
	height: 360rpx;
	padding-top: 30rpx;
	position: relative;
	background: url('https://i.loli.net/2020/12/12/PV23tFOgCKyXpBW.png') repeat fixed center;
}

.center {
	width: 95%;
	height: 300rpx;
	background: white;
	display: flex;
	flex-direction: column;
	margin: 0 auto;
	border-radius: 10rpx;
}

.center_top {
	display: flex;
	flex-direction: row;
	width: 80%;
	height: 160rpx;
	margin: 0 auto;
	margin-top: 20rpx;
	border-bottom: 1rpx solid #eeeeee;
}

.center_img {
	width: 122rpx;
	height: 122rpx;
	border-radius: 50%;
	overflow: hidden;
}

.center_img image {
	width: 100%;
	height: 100%;
	border-radius: 50%;
}

.center_img .user_head {
	width: 100%;
	height: 100%;
}

.center_info {
	display: flex;
	flex-direction: column;
	margin-top: 10rpx;
	margin-left: 60rpx;
}

.center_name {
	font-size: 40rpx;
}

.center_phone {
	color: #bebebe;
}

.center_down {
	display: flex;
	flex-direction: row;
	width: 80%;
	height: 70rpx;
	margin: 0 auto;
	margin-top: 20rpx;
}

.center_rank {
	width: 50%;
	height: 70rpx;
	display: flex;
	flex-direction: row;
}

.rank_text {
	height: 70rpx;
	line-height: 70rpx;
	margin-left: 10rpx;
	color: #aaaaaa;
}

.center_rank image {
	width: 50rpx;
	height: 50rpx;
	margin-top: 10rpx;

}

.center_score {
	width: 50%;
	height: 70rpx;
	display: flex;
	flex-direction: row;
}

.center_score image {
	width: 50rpx;
	height: 50rpx;
	margin-top: 10rpx;

}

.gif-wave {
	position: absolute;
	width: 100%;
	bottom: 0;
	left: 0;
	z-index: 99;
	mix-blend-mode: screen;
	height: 100rpx;
}

.box-cord {
	width: 750rpx;
	height: 300rpx;
	display: flex;
	justify-content: space-around;
}

.cord1 {
	width: 200rpx;
	height: 200rpx;
	margin-top: 20rpx;
	border-radius: 20rpx;
	box-shadow: 0 0 20rpx #d5d5d5;
	display: flex;
	justify-content: center;
	flex-direction: column;
	position: relative;
	image {
		width: 80rpx;
		height: 80rpx;
		position: absolute;
		left: 50%;
		top: 40%;
		transform: translate(-50%, -50%);
		border-radius: 50%;
	}

	span {
		text-align: center;
		padding-top: 120rpx;
		color: #808080;
	}
}

.list-call {
	width: 700rpx;
	height: 600rpx;
	margin: 25rpx;
	border-radius: 20rpx;
	box-shadow: 0 0 20rpx #c2c2c2;
	padding: 10rpx;
}
</style>
