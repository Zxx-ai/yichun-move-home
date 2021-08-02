<template>
	
	<view class="wrap">
		<view @click="go()">
		<drag-ball  :x=300 :y=400 image="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/e652a8ff-1117-46a0-886f-582cd6f9c1be.png" ></drag-ball>
			
		</view>
	
		<u-button @click="clear">清空列表</u-button>
		
		<u-waterfall v-model="flowList" ref="uWaterfall">
			<template v-slot:left="{leftList}">
				<view class="demo-warter" v-for="(item, index) in leftList" :key="index">
					<!-- 警告：微信小程序中需要hx2.8.11版本才支持在template中结合其他组件，比如下方的lazy-load组件 -->
					<u-lazy-load threshold="-450" border-radius="10" :image="item.image" :index="index"></u-lazy-load>
					<view class="demo-title">
						{{item.title}}
					</view>
					<view class="demo-price">
						{{item.price}}
					</view>
					<view class="demo-tag">
						<view class="demo-tag-owner">
								回收
						</view>
						<view class="demo-tag-text">
							放心收购
						</view>
					</view>
					<view class="demo-shop">
						{{item.shop}}
					</view>
					<u-icon name="close-circle-fill" color="#fa3534" size="34" class="u-close" @click="remove(item.id)"></u-icon>
				</view>
			</template>
			<template v-slot:right="{rightList}">
				<view class="demo-warter" v-for="(item, index) in rightList" :key="index">
					<u-lazy-load threshold="-450" border-radius="10" :image="item.image" :index="index"></u-lazy-load>
					<view class="demo-title">
						{{item.title}}
					</view>
					<view class="demo-price">
						{{item.price}}
					</view>
					<view class="demo-tag">
						<view class="demo-tag-owner">
							回收
						</view>
						<view class="demo-tag-text">
							放心收购
						</view>
					</view>
					<view class="demo-shop">
						{{item.shop}}
					</view>
					<u-icon name="close-circle-fill" color="#fa3534" size="34" class="u-close" @click="remove(item.id)"></u-icon>
				</view>
			</template>
		</u-waterfall>
		<u-loadmore bg-color="rgb(240, 240, 240)" :status="loadStatus" @loadmore="addRandomData"></u-loadmore>
		
	</view>
</template>

<script>
	
    import dragBall from "@/components/drag-ball/drag-ball.vue";
	export default { 
		components:{
			dragBall		
		},
		data() {
			return {
				loadStatus: 'loadmore',
				flowList: [],
				list: [
				
					{
						price: '价格面议',
						shop: '宜春好生活旗舰店',
						title: '回收家电,品质保障',
						image: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/8af1670c-00bd-47d1-b4a7-ac445d78f4d7.jpg',
					},
					{
						price: '价格面议',
						title: '回收沙发,表面完好无破损',
						shop: '宜春好生活旗舰店',
						image: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/29dcb27e-baf7-4be3-8d2d-00c5b0151c62.jpg',
					},
					{
						price: '价格面议',
						title: '家用电器',
						shop: '宜春好生活旗舰店',
						image: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/dc2705b7-6c8c-4d33-a744-e97889dbe8e8.jpg',
					},
					{
						price: '价格面议',
						title: '纯棉大床',
						shop: '宜春好生活旗舰店',
						image: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/f2dcd803-0a23-4f2b-a539-d4ea93c8f70b.jpg',
					},
					{
						price: '价格面议',
						title: '家用桌子',
						shop: '宜春好生活旗舰店',
						image: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/7699a19c-8b34-4151-a9f1-981456d84383.jpg',
					},
				]
			}
		},
		onLoad() {
			this.addRandomData();
		},
		onReachBottom() {
			this.loadStatus = 'loading';
			// 模拟数据加载
			setTimeout(() => {
				this.addRandomData();
				this.loadStatus = 'loadmore';
			}, 1000)
		},
		methods: {
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
			},
			addRandomData() {
				for(let i = 0; i < 10; i++) {
					let index = this.$u.random(0, this.list.length - 1);
					// 先转成字符串再转成对象，避免数组对象引用导致数据混乱
					let item = JSON.parse(JSON.stringify(this.list[index]))
					item.id = this.$u.guid();
					this.flowList.push(item);
				}
			},
			remove(id) {
				this.$refs.uWaterfall.remove(id);
			},
			clear() {
				this.$refs.uWaterfall.clear();
			}
		}
	}
</script>

<style>
	/* page不能写带scope的style标签中，否则无效 */
	page {
		background-color: rgb(240, 240, 240);
	}
</style>

<style lang="scss" scoped>
	.demo-warter {
		border-radius: 8px;
		margin: 5px;
		background-color: #ffffff;
		padding: 8px;
		position: relative;
	}
	
	.u-close {
		position: absolute;
		top: 32rpx;
		right: 32rpx;
	}
	
	.demo-image {
		width: 100%;
		border-radius: 4px;
	}
	
	.demo-title {
		font-size: 30rpx;
		margin-top: 5px;
		color: $u-main-color;
	}
	
	.demo-tag {
		display: flex;
		margin-top: 5px;
	}
	
	.demo-tag-owner {
		background-color: $u-type-error;
		color: #FFFFFF;
		display: flex;
		align-items: center;
		padding: 4rpx 14rpx;
		border-radius: 50rpx;
		font-size: 20rpx;
		line-height: 1;
	}
	
	.demo-tag-text {
		border: 1px solid $u-type-primary;
		color: $u-type-primary;
		margin-left: 10px;
		border-radius: 50rpx;
		line-height: 1;
		padding: 4rpx 14rpx;
		display: flex;
		align-items: center;
		border-radius: 50rpx;
		font-size: 20rpx;
	}
	
	.demo-price {
		font-size: 30rpx;
		color: $u-type-error;
		margin-top: 5px;
	}
	
	.demo-shop {
		font-size: 22rpx;
		color: $u-tips-color;
		margin-top: 5px;
	}
</style>