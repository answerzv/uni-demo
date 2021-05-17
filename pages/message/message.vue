<template>
	
	 <view>
		  <view> hello - uni</view>
		 <button type="primary" @click="chooseImg">上传图片</button>
		 <image v-for="item in imgArr" :src="item" @click="prev(item)"></image>
		  <!-- #ifdef H5 -->
		 <view>h5展示</view>
		   <!-- #endif -->
		   
		   <!-- #ifdef MP-WEIXIN-->
		 <view>微信小程序展示</view>
		 <!-- #endif -->
	 </view>
</template>

<script>
	export default{
		data(){
			return{
				imgArr:[]
			}
		},
		methods:{
			
			
			
			chooseImg(){
				console.log('上传图片'),
				uni.chooseImage({
					count:5,
					success:re=>{
						console.log(re)
						this.imgArr = re.tempFilePaths
					}
				})
			},
			
			prev(cc){  //图片的预览
				console.log(cc)
				uni.previewImage({
					current:cc,
					urls:this.imgArr,
					indicator:'number'
				})
			},
			
			onLoad(){ //生命周期函数页面渲染时运行
			    // #ifdef H5
				console.log('我希望h5中打印')
				// #endif
				
				// #ifdef MP-WEIXIN
				console.log('我希望小程序中打印')
				// #endif
			}
		}
	}
</script>

<style>
	/* #ifdef H5 */
	view{
		color: hotpink;
	}
	/* #endif */
	
	/* #ifdef  MP-WEIXIN */
	view{
		color: #0000FF;
	}
	/* #endif */
</style>
