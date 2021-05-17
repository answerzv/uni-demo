<template>
	   <view>
		   联系我们
		   
		   <view>
		       <uni-calendar 
		       :insert="true"
		       :lunar="true" 
		       :start-date="'2019-3-2'"
		       :end-date="'2019-5-20'"
		       @change="change"
		        ></uni-calendar>
		   </view>
	   </view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		
		methods:{
			change(e){ //事件对象
				console.log('日历',e)
			}
		}
	}
</script>

<style>
</style>
