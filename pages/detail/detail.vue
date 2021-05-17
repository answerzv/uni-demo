<template>
	<view>
		<view>
			<text>详情页</text>
			<text>唱歌跳舞打篮球</text>
		</view>
		<view>
			<text selectable="true">唱歌跳舞打篮球</text> <!--selectable仅用于App、H5-->
		</view>
		<view>
			<text selectable="true" space="ensp">唱歌    跳舞打篮球</text> <!--selectable仅用于App、H5-->
		</view>
		<view>
			<text selectable="true" space="emsp">唱歌    跳舞打篮球</text> <!--selectable仅用于App、H5-->
		</view>
		<view>
			<text selectable="true" space="nbsp" style="font-size: 40px;">唱歌   跳舞打篮球</text> <!--selectable仅用于App、H5-->
		</view>
		
		<view class="box2" hover-class="box2-ac">
			<view class="box" hover-class="box-ac"  hover-stop-propagation  :hover-start-time="2000"></view>
		</view>
		
		<view>
			<button class="boxcut"hover-class="cut"	>按钮</button>
			<button type="warn" size="mini" disabled>按钮</button>
			<button type="primary" loading	>按钮</button>
			<button type="warn" plain loading  >按钮</button>
			<image src="http://up.deskcity.org/pic_source/81/8c/08/818c08880506db0b431e87b03b22ffe4.gif" mode="aspectFill"></image>
			<image src="http://up.deskcity.org/pic_source/81/8c/08/818c08880506db0b431e87b03b22ffe4.gif" mode="aspectFit"></image>
			<view  style="display: flex;">
				<image src="http://up.deskcity.org/pic_source/81/8c/08/818c08880506db0b431e87b03b22ffe4.gif" mode="aspectFill" class="as" ></image>
				<image src="http://up.deskcity.org/pic_source/81/8c/08/818c08880506db0b431e87b03b22ffe4.gif" mode="aspectFit" class="as"></image>
			</view>
			
		</view>
		
		
		
		
	</view>
</template>

<script>
	export default{
		onLoad(op){
			console.log(op)
		}
	}
</script>

<style>
	.box{
		width: 100px;
		height: 100px;
		background-color: #4CD964;
	}
	
	.box-ac{
		 background-color: red;
	}
	
	.box2{
		width: 200px;
		height: 200px;
		background-color: #2C405A;
	}
	
	.box2-ac{
		background-color: #e91e63;
	}
	
	.boxcut{
		background-color: #4CD964;
	}
	
	.cut{
		background-color: #007AFF;
	}
	
	.as{
		width: 100px;
		height: 100px;
	}
	
</style>
