<template>
	<view class="box">
	   <hm-reply-card :options="options"></hm-reply-card>
	</view>
</template>

<script>
	import HmReplyCard from '@/components/hm-reply-card/index.vue'
	export default {
		   components: { HmReplyCard },
		data() {
			return {
				 options: {
				          newComments: '新评论',
				          dot:
				            '/static/hm-reply-card/images/img_26225_0_4.png',
				          dot_2:
				            '/static/hm-reply-card/images/img_26225_0_5.png',
				          dot_3:
				            '/static/hm-reply-card/images/img_26225_0_6.png',
				          shopCreditLv1:
				            'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/44931050-7313-44e5-a038-f89301999b59.jpg',
				          desc: '小猫咪已经回答了视频的评论',
				          twoDaysAgo: '两天前',
				          creditLv1:
				            'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/350c4772-5e61-4ffb-91b5-1ce87bc87563.jpg',
				          desc_2: '今生缘回答了视频的评论…',
				          num: '3',
				          daysAgo: '天前',
				          lanzuanLv1:
				            'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/739b6a2d-144a-4b67-bcfc-3d73de148ce3.jpg',
				          desc_3: '马克一天评论了视频',
				          num_2: '4',
				          daysAgo_2: '天前',
				          huangzuanLv1:
				            'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-imgbed/356733f1-a1ea-4be9-a8ca-eedfeee666a4.jpg',
				          desc_4: '网友已经评论视频',
				          num_3: '5',
				          daysAgo_3: '天前'
				        }
				
			};
		},
		methods:{
			 onClick: function(e) {
			      console.log('onClick');
			    }
			
		}
		
	};
</script>

<style  scoped lang="scss">

</style>
