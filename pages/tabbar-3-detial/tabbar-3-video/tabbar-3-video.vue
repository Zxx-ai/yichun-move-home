<template>
	<view class="content">
	
		<view class="sp-top">
			<yfsVideo
			   :src="src" 
			   :danmu-list="danmuList" 
			   :videoTitle="videoTitle"></yfsVideo>
		</view>
	   <view>
	       <view class="uni-padding-wrap">
	           <!-- 评论区 start -->
	           <view class="uni-comment">
	               <view class="uni-comment-list">
	                   <view class="uni-comment-face">
	                       <image src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/356733f1-a1ea-4be9-a8ca-eedfeee666a4.jpg" mode="widthFix"></image>
	                   </view>
	                   <view class="uni-comment-body">
	                       <view class="uni-comment-top">
	                           <text>网友</text>
	                       </view>
	                       <view class="uni-comment-date">
	                           <text>08/10 08:12</text>
	                       </view>
	                       <view class="uni-comment-content">服务真的不错</view>
	                   </view>
	               </view>
	               <view class="uni-comment-list">
	                   <view class="uni-comment-face">
	                       <image src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/739b6a2d-144a-4b67-bcfc-3d73de148ce3.jpg" mode="widthFix"></image>
	                   </view>
	                   <view class="uni-comment-body">
	                       <view class="uni-comment-top">
	                           <text>马克一天</text>
	                       </view>
	                       <view class="uni-comment-content">价格挺良心的</view>
	                   </view>
	               </view>
	               <view class="uni-comment-list">
	                   <view class="uni-comment-face">
	                       <image src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/350c4772-5e61-4ffb-91b5-1ce87bc87563.jpg" mode="widthFix"></image>
	                   </view>
	                   <view class="uni-comment-body">
	                       <view class="uni-comment-top">
	                           <text>今生缘</text>
	                       </view>
						   <view class="uni-comment-date">
						       <text>08/10 07:55</text>
						   </view>
	                       <view class="uni-comment-content">下次推荐给朋友</view>
	                    
	                   </view>
	               </view>
	               <view class="uni-comment-list">
	                   <view class="uni-comment-face">
	                       <image src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/44931050-7313-44e5-a038-f89301999b59.jpg" mode="widthFix"></image>
	                   </view>
	                   <view class="uni-comment-body">
	                       <view class="uni-comment-top">
	                           <text>小猫咪</text>
	                       </view>
	                       <view class="uni-comment-content">支持，支持!</view>
	                       <view class="uni-comment-date">
	                           <view>2天前</view>
	                           <view class="uni-comment-replay-btn">5回复</view>
	                       </view>
	                   </view>
	               </view>
	           </view>
	       </view>
	   </view>

	</view>
</template>

<script>
	
	import yfsVideo from '../../../components/yfs-video/yfs-video.vue'

	export default {
		  components:{
		        yfsVideo
		    },
		data() {
			return {
				        title: "评论界面",
				  src: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/d278e3ae-6eea-4c79-9808-6baf173039b7.mp4',
				            danmuList: [{
				                    text: '服务真的不错',
				                    color: '#ff0000',
				                    time: 1
				                },
				                {
				                    text: '价格挺良心的',
				                    color: '#ffffff',
				                    time: 3
				                },
				                {
				                    text: '下次推荐给朋友',
				                    color: '#fff',
				                    time: 5
				                },  {
				                    text: '支持，支持!',
				                    color: '#fff',
				                    time: 10
				                }
								
								
								
								],
				            videoCurrTime:0,
				            videoTitle:"zhemvopswemvop    wjfopjeowjmpiojm"
					
							
				
			}
		},
		onLoad() {

		},
		methods: {
  getTimeVideo:function(e){
            console.log(e);
        },
		}
	}
</script>

<style scoped lang="scss">

    .uni-padding-wrap {
        padding: 30upx;
    }

    view {
        font-size: 28upx;
    }

    .uni-comment {
        padding: 5rpx 0;
        display: flex;
        flex-grow: 1;
        flex-direction: column;
    }

    .uni-comment-list {
        flex-wrap: nowrap;
        padding: 10rpx 0;
        margin: 10rpx 0;
        width: 100%;
        display: flex;
    }

    .uni-comment-face {
        width: 70upx;
        height: 70upx;
        border-radius: 100%;
        margin-right: 20upx;
        flex-shrink: 0;
        overflow: hidden;
    }

    .uni-comment-face image {
        width: 100%;
        border-radius: 100%;
    }

    .uni-comment-body {
        width: 100%;
    }

    .uni-comment-top {
        line-height: 1.5em;
        justify-content: space-between;
    }

    .uni-comment-top text {
        color: #0A98D5;
        font-size: 24upx;
    }

    .uni-comment-date {
        line-height: 38upx;
        flex-direction: row;
        justify-content: space-between;
        display: flex !important;
        flex-grow: 1;
    }

    .uni-comment-date view {
        color: #666666;
        font-size: 24upx;
        line-height: 38upx;
    }

    .uni-comment-content {
        line-height: 1.6em;
        font-size: 28upx;
        padding: 8rpx 0;
    }

    .uni-comment-replay-btn {
        background: #FFF;
        font-size: 24upx;
        line-height: 28upx;
        padding: 5rpx 20upx;
        border-radius: 30upx;
        color: #333 !important;
        margin: 0 10upx;
    }
	
	
</style>
