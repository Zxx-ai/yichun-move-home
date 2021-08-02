<template>
	
		<view class="contact">
		
				<map name=""  :longitude="jingdu" :latitude="weidu" :markers="marks" scale="15" :style="{height: nowMapIndex ? nintyPercentScreenHeight : seventyPercentScreenHeight,width:'750rpx',height:'100vh'}"></map>
				
			</view>
	
</template>

<script>
	export default {
		data() {
			return { 
				title: 'Hello',
				jingdu:114.41168446753309,
				weidu:27.800719599497604,
		        marks:[{longitude:114.41168446753309,
				latitude:27.800719599497604,
				iconPath:'https://i.loli.net/2020/12/09/xpaEkQIiGUt4TJD.png',
				width:30,height:30,
				title:'宜春市袁州区官员路515号',
				　 label:{//为标记点旁边增加标签   //因背景颜色H5不支持
				  　　 content:'宜春好生活家政',//文本
				　　　　color:'red',//文本颜色
				       // 　　fontSize:24,//文字大小
					   
				          // x:113.0117220184593,//label的坐标，原点是 marker 对应的经纬度
				          // y:27.500581987720324,//label的坐标，原点是 marker 对应的经纬度 
				       //    borderWidth:12,//边框宽度
				       //    borderColor:'pink',//边框颜色    
				       　　borderRadius:20,//边框圆角                        
				     // 　　bgColor:'black',//背景色
				      　　padding:5,//文本边缘留白
				        // textAlign:'right'//文本对齐方式。
				   },
		callout:{//自定义标记点上方的气泡窗口 点击有效
		  　　content:'宜春市袁州区官员路55号',//文本
		  　　color:'#ffffff',//文字颜色
		  　　fontSize:14,//文本大小
		  　　borderRadius:2,//边框圆角
		 　　 bgColor:'#00c16f',//背景颜色
		  　　display:'ALWAYS',//常显
		  }
				},
				
				],
					nowMapIndex:true,
								phoneHeight:'',//屏幕高
								phoneWidth:'',//屏幕宽
			}
		},
		onLoad() {
  //                  uni.getLocation({
		// 	success: res => {
		// 		console.log('location success', res)
		// 		uni.openLocation({
		// 			latitude: res.latitude,
		// 			longitude: res.longitude,
		// 			scale: 18
		// 		})
		// 	}
		// })
		},
		onReady(){
					// 计算屏幕高度 ，宽度
					let _this = this;
					uni.getSystemInfo({
						success(res) {
							 _this.phoneHeight = res.windowHeight;
							 _this.phoneWidth = res.windowWidth
						}
					});
				},
				computed:{//计算
					nintyPercentScreenHeight(){//百分之九十的屏幕高
						if(this.phoneHeight!=='' && this.phoneWidth!==''){
							return 750/(this.phoneWidth)*(this.phoneHeight)*0.9+'rpx'
						}else{
							return '1250rpx'
						}
						
					},
					seventyPercentScreenHeight(){//百分之七十的屏幕高
						if(this.phoneHeight!=='' && this.phoneWidth!==''){
							return 750/(this.phoneWidth)*(this.phoneHeight)*0.7+'rpx'
						}else{
							return '1000rpx'
						}
						
					},
				},	
		methods: {
           phone(){
				uni.makePhoneCall({
				    phoneNumber: '114' //仅为示例
				});
			}
		}
	}
</script>

<style>


</style>
