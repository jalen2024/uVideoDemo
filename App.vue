<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	@import url('./components/colorui/icon.css');
	@import url('./components/colorui/main.css');
	@import url('./components/colorui/animation.css');
	*{
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}
	.content{
		width: 100%;
		height: 100%;
		background-color: #F7F7F7;
	}
</style>
