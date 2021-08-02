	<template>
		
		<view class="box-tuw">
			<u-card :title="title" :sub-title="subTitle" :thumb="thumb">
				<view class="" slot="body">
					<view class="u-body-item u-flex u-border-bottom u-col-between u-p-t-0">
						<view class="u-body-item-title u-line-2">宜春好生活搬家，用爱的力量搬出温暖温馨的家。</view>
						<image src="https://i.loli.net/2020/12/13/71MZQzGTJEfLPYh.jpg" mode="aspectFill"></image>
					</view>
					<view class="u-body-item u-flex u-row-between u-p-b-0">
						<view class="u-body-item-title u-line-2">宜春搬家，公众号来袭啦，现在关注即可知道最新资讯~</view>
						<image src="https://i.loli.net/2020/12/13/i4nzrqxcSRBMaeC.png" mode="aspectFill"></image>
					</view>
				</view>
				<view class="" slot="foot"><u-icon name="chat-fill" size="34" color="" label="30评论"></u-icon></view>
			</u-card>
		</view>
		
	</template>
	
	<script>
	export default {
	data() {
		return {
			title: '素胚勾勒出青花，笔锋浓转淡',
			subTitle: '2020-05-15',
			thumb: 'http://pic2.sc.chinaz.com/Files/pic/pic9/202002/hpic2119_s.jpg',
		};
	}
};
</script>

<style scoped lang="scss">
	.u-card-wrap { 
		background-color: $u-bg-color;
		padding: 1px;
	}
	
	.u-body-item {
		font-size: 32rpx;
		color: #333;
		padding: 20rpx 10rpx;
	}
		
	.u-body-item image {
		width: 120rpx;
		flex: 0 0 120rpx;
		height: 120rpx;
		border-radius: 8rpx;
		margin-left: 12rpx;
	}
</style>