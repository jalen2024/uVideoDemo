<template>
	<view class="content">
		<!--  自定义导航栏 -->
		<NavBack></NavBack>
		<!--  播放器 -->
		<view 
		class="video-player"
		:style="'background-image: url('+ movie.src +'); background-repeat: no-repeat;background-size: 100% 230px;'"
		>
			<text class="player-icon text-white cuIcon-playfill" @tap="goSplayer"></text>
		</view>
		<!--  影片详情 -->
		<view class="video-content">
			<view class="video-title">
				<view class="video-name">
					 {{movie.title}}
				</view>
				<view class="video-sd">
					 简介
				</view>
				<text class="video-more text-gray" :class="showDesc?'cuIcon-fold':'cuIcon-unfold'" @tap="ifShowDesc"></text>
			</view>
			<view class="video-desc">
				<view class="actors">
					 主演:{{movie.actors}}
				</view>
				<view class="desc" v-show="showDesc">
					{{movie.desc}}
				</view>
			</view>
		</view>
		<!--  选项 -->
		<view class="video-opt">
			<view class="opt bg-gradual-blue">
				<text class="opt-icon text-white cuIcon-down"></text>
				<view class="opt-name">
					下载
				</view>
			</view>
			<view class="opt bg-gradual-blue">
				<text class="opt-icon text-white cuIcon-pick"></text>
				<view class="opt-name">
					 浏览器打开
				</view>
			</view>
			<view class="opt bg-gradual-blue">
				<text class="opt-icon text-white cuIcon-forwardfill"></text>
				<view class="opt-name">
					分享
				</view>
			</view>
		</view>
		<!--  资源列表 -->
		<view class="video-source-title">
			<view class="source-title">
				 选择资源
			</view>
			<view class="source-desc">
				无法观看尝试切换资源
			</view>
		</view>
		<view class="video-source">
			<view class="source bg-gradual-blue">
				 超简云
			</view>
			<view class="source bg-gradual-blue">
				  百度云
			</view>
		</view>
		<!--  选集 -->
		<view class="video-choise-title">
			<view class="choise-title">
				 选集
			</view>
			<view class="source-name">
				 当前资源: 超简云
			</view>
		</view>
		
		<view class=" video-choise">
			<view class="choise bg-gradual-blue">
				 第一集
			</view>
			<view class="choise bg-gradual-blue">
				 第二集
			</view>
			<view class="choise bg-gradual-blue">
				 第三集
			</view>
			<view class="choise bg-gradual-blue">
				 第四集
			</view>
			<view class="choise bg-gradual-blue">
				 第五集
			</view>
			<view class="choise bg-gradual-blue">
				 第六集
			</view>
			<view class="choise bg-gradual-blue">
				 第七集
			</view>
			<view class="choise bg-gradual-blue">
				 第八集
			</view>
			<view class="choise bg-gradual-blue">
				 第九集
			</view>
			<view class="choise bg-gradual-blue">
				 第十集
			</view>
			<view class="choise bg-gradual-blue">
				 第十一集
			</view>
		</view>
		<!-- 撑图区域 -->
		<view class="other">
			<view class="comment">
				 热门评论
			</view>
			<view class="comment-content">
				 没有更多了
			</view>
		</view>
		
	</view>
</template>

<script>
	import NavBack from '../../components/NavBack/index.vue';
	export default {
		components:{
			NavBack,
		},
		data() {
			return {
				showDesc: false,
				movie:{
					'id': 0,
					'title': '大约在冬季 2019',
					'src': 'https://cn2.3days.cc/1577875712879260.jpeg',
					'actors': '马思纯, 霍建华, 魏大勋, 张瑶, 林柏宏, 文淇, 侯佩岑, 齐秦',
					'desc': '　1991年齐秦狂飙演唱会上，北师大才女安然（马思纯 饰）和来自台北的摄影师齐啸（霍建华 饰）因缘相识，曲终人散后再度重逢的二人陷入热恋，然而不是勇敢就一定能拥有爱，不是所有再见都能再见！在漂泊岁月中，弄丢了挚爱的我们，是否还能安然无恙？没有我的日子里，你是否能保重自己？2019年，齐啸和安然能否重逢？',
					'url': 'https://jx.7639616.com/?url=https://cn7.kankia.com/hls/20200101/5c361debcd70cbd3cd118bc9d24186a4/1577874894/index.m3u8'
				}
			}
		},
		methods: {
			ifShowDesc(){
				this.showDesc = !this.showDesc;
			},
			goSplayer(){
				uni.setStorage({
					key: 'video-name',
					data: 'https://jx.7639616.com/?url=https://cn7.kankia.com/hls/20200101/5c361debcd70cbd3cd118bc9d24186a4/1577874894/index.m3u8',
					success() {
						console.log('success');
					}
				})
				uni.navigateTo({
					url: "../Splayer/Splayer"
				})
			},
		}
	}
</script>

<style>
	@import url('./index.css');
</style>
