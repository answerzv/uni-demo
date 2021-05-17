<script>
	export default {
		// 应用的生命周期函数
		onLaunch: function() {
			console.log('App Launch 应用启动之后渲染完成触发 ')
		},
		onShow: function() {
			console.log('App Show应用显示出来就会触发 应用关闭再打开再次触发 ')
		},
		onHide: function() {
			console.log('App Hide 应用隐藏就会触发')
		},
		onError:function(err){
			console.log('出现异常了',err)
		}
	}
</script>

<style>
	/*每个页面公共css */
	@import url("./static/fonts/iconfont.css");
	.box{
		background-color: #4CD964
	}
</style>
