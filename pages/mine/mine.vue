<template>
	<view class="content">
		 <!-- 头部 -->
		 <view class="mine-header bg-gradual-blue">
			 <view class="mine-header-title">
			 	 我的
			 </view>
			 <view class="usr-icon">
			 	<image src="../../static/images/new1.jpg" mode=""></image>
			 </view>
			 <view class="usr-name">
			 	 羊毛党 Top1
			 </view>
		</view>
		<!-- 设置项 -->
		<view class="mine-opt">
			<view 
			class="opt"
			v-for="(item, index) in menuList"
			:key="index"
			>
				<text class="opt-icon text-gray" :class="'cuIcon-'+ item.icon"></text>
				<view class="opt-name">
					{{item.name}}
				</view>
			</view>

			<view class="opt">
				
			</view>
			<view class="opt">
				
			</view>
		</view>
		<!-- about -->
		<view class="about">
			<view class="about-title">
				 关于我们
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				menuList:[
					{
						'id': 0,
						'icon': 'down',
						'name': '我的缓存'
					},{
						'id': 1,
						'icon': 'footprint',
						'name': ' 播放历史'
					},{
						'id': 2,
						'icon': 'favor',
						'name': '我的收藏'
					},{
						'id': 3,
						'icon': 'message',
						'name': '我的消息'
					},{
						'id': 4,
						'icon': 'settings',
						'name': '用户设置'
					},{
						'id': 5,
						'icon': 'edit',
						'name': '意见反馈'
					},{
						'id': 6,
						'icon': 'order',
						'name': '检查更新'
					}
				]
			}
		},
		methods: {
			goDetail_1(){
				uni.navigateTo({
					url: '../history/history'
				})
			},
			goDetail_2(){
				uni.navigateTo({
					url: '../favor/favor'
				})
			},
		}
	}
</script>

<style>
	@import url('./index.css');
</style>
