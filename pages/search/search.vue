<template>
	<view class="content">
		<!--  搜索栏 -->
		<view class="nav-box bg-gradual-blue">
			<text class="nav-back text-white cuIcon-back" @tap="goBack"></text>
			<view class="nav-search">
				<text class="nav-search-icon text-gray cuIcon-search"></text>
				<input 
				class="nav-input" 
				type="text" 
				value=""
				confirm-type="search"
				@input="onKeyInput"
				@confirm="onKeyDown"
				/>
			</view>
		</view>
		<!--  默认热门 --> 
		<view class="default-list" v-show="defaultRec">
			<view class="item">
				<view class="item-title bg-gradual-blue">
					 <text class="item-icon text-white cuIcon-hotfill"></text>
					 <view class="item-name">
					 	 必看 Top25
					 </view>
				</view>
				<image src="../../static/images/new1.jpg" mode=""></image>
			</view>
			<view class="item">
				<view class="item-title bg-gradual-blue">
					 <text class="item-icon text-white cuIcon-hotfill"></text>
					 <view class="item-name">
					 	  漫威大电影漫威大电影
					 </view>
				</view>
				<image src="../../static/images/new1.jpg" mode=""></image>
			</view>
			<view class="item">
				<view class="item-title bg-gradual-blue">
					 <text class="item-icon text-white cuIcon-hotfill"></text>
					 <view class="item-name">
					 	 必看 Top25
					 </view>
				</view>
				<image src="../../static/images/new1.jpg" mode=""></image>
			</view>
			<view class="item">
				<view class="item-title bg-gradual-blue">
					 <text class="item-icon text-white cuIcon-hotfill"></text>
					 <view class="item-name">
					 	 必看 Top25
					 </view>
				</view>
				<image src="../../static/images/new1.jpg" mode=""></image>
			</view>
			<view class="item">
				<view class="item-title bg-gradual-blue">
					 <text class="item-icon text-white cuIcon-hotfill"></text>
					 <view class="item-name">
					 	 必看 Top25
					 </view>
				</view>
				<image src="../../static/images/new1.jpg" mode=""></image>
			</view>
			<view class="item">
				<view class="item-title bg-gradual-blue">
					 <text class="item-icon text-white cuIcon-hotfill"></text>
					 <view class="item-name">
					 	 必看 Top25
					 </view>
				</view>
				<image src="../../static/images/new1.jpg" mode=""></image>
			</view>
			<view class="item">
				<view class="item-title bg-gradual-blue">
					 <text class="item-icon text-white cuIcon-hotfill"></text>
					 <view class="item-name">
					 	 必看 Top25
					 </view>
				</view>
				<image src="../../static/images/new1.jpg" mode=""></image>
			</view>
			<view class="item">
				<view class="item-title bg-gradual-blue">
					 <text class="item-icon text-white cuIcon-hotfill"></text>
					 <view class="item-name">
					 	 必看 Top25
					 </view>
				</view>
				<image src="../../static/images/new1.jpg" mode=""></image>
			</view>
			<view class="item">
				<view class="item-title bg-gradual-blue">
					 <text class="item-icon text-white cuIcon-hotfill"></text>
					 <view class="item-name">
					 	  漫威大电影漫威大电影
					 </view>
				</view>
				<image src="../../static/images/new1.jpg" mode=""></image>
			</view>
			<view class="item">
				<view class="item-title bg-gradual-blue">
					 <text class="item-icon text-white cuIcon-hotfill"></text>
					 <view class="item-name">
					 	  漫威大电影漫威大电影
					 </view>
				</view>
				<image src="../../static/images/new1.jpg" mode=""></image>
			</view>
		</view>
		<!-- 默认操作 -->
		<view class="default-opt" v-show="defaultRec">
			<view class="opt bg-gradual-blue">
				<text class="opt-icon text-white cuIcon-list"></text>
				<view class="opt-name">
					更多精彩
				</view>
			</view>
			<view class="opt bg-gradual-blue">
				<text class="opt-icon text-white cuIcon-refresh"></text>
				<view class="opt-name">
					换一批
				</view>
			</view>
		</view>
		<!-- 搜索结果 -->
		<view class="video-list" v-show="ifSearch">
		 	<view class="single-video">
		 		<image src="../../static/images/new1.jpg" mode=""></image>
		 		<view class="video-name">
		 			 勇敢者的游戏
		 		</view>
		 	</view>
			<view class="single-video">
				<image src="../../static/images/new1.jpg" mode=""></image>
				<view class="video-name">
					 勇敢者的游戏
				</view>
			</view>
			<view class="single-video">
				<image src="../../static/images/new1.jpg" mode=""></image>
				<view class="video-name">
					 勇敢者的游戏
				</view>
			</view>
			<view class="single-video">
				<image src="../../static/images/new1.jpg" mode=""></image>
				<view class="video-name">
					 勇敢者的游戏
				</view>
			</view>
			<view class="single-video">
				<image src="../../static/images/new1.jpg" mode=""></image>
				<view class="video-name">
					 勇敢者的游戏勇敢者的
				</view>
			</view>
			<view class="single-video">
				<image src="../../static/images/new1.jpg" mode=""></image>
				<view class="video-name">
					 勇敢者的游戏勇敢者的
				</view>
			</view>
			<view class="single-video">
				<image src="../../static/images/new1.jpg" mode=""></image>
				<view class="video-name">
					 勇敢者的游戏勇敢者的
				</view>
			</view>
			<view class="single-video">
				<image src="../../static/images/new1.jpg" mode=""></image>
				<view class="video-name">
					 勇敢者的游戏勇敢者的
				</view>
			</view>
			<view class="single-video">
				<image src="../../static/images/new1.jpg" mode=""></image>
				<view class="video-name">
					 勇敢者的游戏勇敢者的
				</view>
			</view>
			<view class="single-video">
				<image src="../../static/images/new1.jpg" mode=""></image>
				<view class="video-name">
					 勇敢者的游戏勇敢者的
				</view>
			</view>
			<view class="single-video">
				<image src="../../static/images/new1.jpg" mode=""></image>
				<view class="video-name">
					 勇敢者的游戏勇敢者的
				</view>
			</view>
			
		</view>
		<!-- 没有更多了 -->
		<view class="not-have-anymore" v-show="ifSearch">
			没有更多了
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				inputValue: '',
				defaultRec: true,
				ifSearch: false
			}
		},
		methods: {
			goBack(){
				history.back();
			},
			onKeyInput: function (e) {
				this.inputValue = e.target.value;
			},
			onKeyDown: function (e) {
				console.log(e.target.value)
			}
		}
	}
</script>

<style>
	@import url('./index.css');
</style>
