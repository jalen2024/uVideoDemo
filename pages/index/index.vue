<template>
	<view class="content">
		<!-- 自定义导航栏 -->
		<Nav></Nav>
		<!--  轮播图  -->
		<swiper class="card-swiper square-dot" :indicator-dots="true" :circular="true"
		 :autoplay="true" interval="5000" duration="500" @change="cardSwiper" indicator-color="#8799a3"
		 indicator-active-color="#0081ff">
			<swiper-item v-for="(item,index) in swiperList" :key="index" :class="cardCur==index?'cur':''">
				<view class="swiper-item" @tap="goDetail">
					<image :src="item.url" mode="aspectFill" v-if="item.type=='image'" ></image>
					<video :src="item.url" autoplay loop muted :show-play-btn="false" :controls="false" objectFit="cover" v-if="item.type=='video'"></video>
				</view>
			</swiper-item>
		</swiper>
		<!-- 简闻 -->
		<view class="simple-news-title">
			<view class="news-title">
				 简闻
			</view>
			<view class="news-content">
				<view class="news-type">
					 热议
				</view>
				<view class="news-msg">
					公布,刘亦菲主唱' 花木兰'刘亦菲主唱' 花木兰'刘亦菲主唱' 花木兰'
				</view>
			</view>
			<view class="more">
				<text class="text-gray cuIcon-right"></text>
			</view>
		</view>
		<!-- news -->
		<view class="news-box">
			<view class="news" v-for="(item, index) in simpleNews" :key="index">
				<image class="news-pic" :src="item.src" mode=""></image>
				<text class="news-desc">{{item.title}}</text>
			</view>
		</view>
		<!-- 电影模块 -->
		<view class="module-title">
			<view class="title-ico">
				<text class="text-gray cuIcon-video"></text>
			</view>
			<view class="title-name">
				电影
			</view>
			<view class="title-more" @tap="goCategory">
				<text class="text-gray cuIcon-right"></text>
			</view>
		</view>
		<!--  影片列表模块 -->
		<view class="module-list-one">
			<view class="list-one" @tap="goDetail">
				<image src="https://1img.hitv.com/preview/cms_icon/2020/1/4/01/20200104155613840.jpg_2048x550.jpg" mode=""></image>
				<view class="list-one-name">
					 大约在冬季 2019
				</view>
			</view>
		</view>
		<view class="module-list-other">
			<view class="list-other" v-for="(item, index) in movieList" :key="index" @tap="goDetail">
				<image :src="item.src" mode=""></image>
				<view class="list-other-name">
					{{item.title}}
				</view>
			</view>
		</view>
		<!-- 电视剧模块 -->
		<view class="module-title">
			<view class="title-ico">
				<text class="text-gray cuIcon-cardboard"></text>
			</view>
			<view class="title-name">
				剧集
			</view>
			<view class="title-more" @tap="goCategory">
				<text class="text-gray cuIcon-right"></text>
			</view>
		</view>
		<!-- 影片列表模块 -->
		<view class="module-list-one">
			<view class="list-one" @tap="goDetail">
				<image src="https://1img.hitv.com/preview/cms_icon/2020/1/4/01/20200104155613840.jpg_2048x550.jpg" mode=""></image>
				<view class="list-one-name">
					大约在冬季 2019
				</view>
			</view>
		</view>
		<view class="module-list-other">
			<view class="list-other" v-for="(item, index) in movieList" :key="index" @tap="goDetail">
				<image :src="item.src" mode=""></image>
				<view class="list-other-name">
					{{item.title}}
				</view>
			</view>
		</view>
		<!-- 动漫模块 -->
		<view class="module-title">
			<view class="title-ico">
				<text class="text-gray cuIcon-skin"></text>
			</view>
			<view class="title-name">
				动漫
			</view>
			<view class="title-more" @tap="goCategory">
				<text class="text-gray cuIcon-right"></text>
			</view>
		</view>
		<!-- 影片列表模块 -->
		<view class="module-list-one">
			<view class="list-one" @tap="goDetail">
				<image src="https://1img.hitv.com/preview/cms_icon/2020/1/4/01/20200104155613840.jpg_2048x550.jpg" mode=""></image>
				<view class="list-one-name">
					 大约在冬季 2019
				</view>
			</view>
		</view>
		<view class="module-list-other">
			<view class="list-other" v-for="(item, index) in movieList" :key="index" @tap="goDetail">
				<image :src="item.src" mode=""></image>
				<view class="list-other-name">
					{{item.title}}
				</view>
			</view>
		</view>
		<!-- 微电影 -->
		<view class="module-title">
			<view class="title-ico">
				<text class="text-gray cuIcon-record"></text>
			</view>
			<view class="title-name">
				 微电影
			</view>
			<view class="title-more" @tap="goCategory">
				<text class="text-gray cuIcon-right"></text>
			</view>
		</view>
		<!--  影片列表模块 -->
		<view class="module-list-one">
			<view class="list-one" @tap="goDetail">
				<image src="https://1img.hitv.com/preview/cms_icon/2020/1/4/01/20200104155613840.jpg_2048x550.jpg" mode=""></image>
				<view class="list-one-name">
					 大约在冬季 2019
				</view>
			</view>
		</view>
		<view class="module-list-other">
			<view class="list-other" v-for="(item, index) in movieList" :key="index" @tap="goDetail">
				<image :src="item.src" mode=""></image>
				<view class="list-other-name">
					{{item.title}}
				</view>
			</view>
		</view>
		<!-- end -->
	</view>
</template>

<script>
	import Nav from '../../components/Navigator/index.vue'
	export default {
		components:{
			Nav,
		},
		data() {
			return {
				cardCur: 0,
				swiperList: [{
						id: 0,
						type: 'image',
						url: 'https://1img.hitv.com/preview/cms_icon/2020/1/4/01/20200104155613840.jpg_2048x550.jpg'
					}, {
						id: 1,
						type: 'image',
						url: 'https://3img.hitv.com/preview/cms_icon/2020/1/26/01/20200126154228745.jpg_2048x550.jpg',
					}, {
						id: 2,
						type: 'image',
						url: 'https://3img.hitv.com/preview/cms_icon/2020/1/26/01/20200126154228745.jpg_2048x550.jpg'
					}
				],
				simpleNews:[{
						'id': 0,
						'title': '各行各业复工进行时',
						'src': 'http://hiphotos.baidu.com/news/crop%3D0%2C0%2C665%2C362%3Bq%3D80%3B/sign=8c577686c11b9d169e88c021ceee98bf/dcc451da81cb39db4c6c830fdf160924ab18303f.jpg'
					},{
						'id': 1,
						'title': '纸短情长, 她藏起一封"遗书", 为己壮行',
						'src': 'http://hiphotos.baidu.com/news/crop%3D0%2C0%2C665%2C362%3Bq%3D80%3B/sign=05b270e288d6277ffd5d687815083300/342ac65c10385343794163789c13b07ecb8088d9.jpg'
					},{
						'id': 2,
						'title': '奔忙在武汉雷神山医院的"摆渡人"',
						'src': 'http://hiphotos.baidu.com/news/crop%3D0%2C0%2C665%2C362%3Bq%3D80%3B/sign=3462ff1a84d4b31ce473cefbbae60b4f/b7003af33a87e9504ba517351f385343fbf2b43d.jpg'
					},{
						'id': 3,
						'title': '法国禁止千人以上的聚集游行',
						'src': 'http://hiphotos.baidu.com/news/crop%3D0%2C0%2C665%2C362%3Bq%3D80%3B/sign=cb886138f71986185508b5c477dd0243/023b5bb5c9ea15ce4e400450b9003af33a87b239.jpg'
					},	
				],
				movieList:[{
						'id': 0,
						'title': '大约在冬季 2019',
						'src': 'https://cn2.3days.cc/1577875712879260.jpeg',
						'actors': ['马思纯','霍建华', '魏大勋', '张瑶', '林柏宏', '文淇', '侯佩岑', '齐秦'],
						'desc': '　1991年齐秦狂飙演唱会上，北师大才女安然（马思纯 饰）和来自台北的摄影师齐啸（霍建华 饰）因缘相识，曲终人散后再度重逢的二人陷入热恋，然而不是勇敢就一定能拥有爱，不是所有再见都能再见！在漂泊岁月中，弄丢了挚爱的我们，是否还能安然无恙？没有我的日子里，你是否能保重自己？2019年，齐啸和安然能否重逢？',
						'url': 'https://jx.7639616.com/?url=https://cn7.kankia.com/hls/20200101/5c361debcd70cbd3cd118bc9d24186a4/1577874894/index.m3u8'
					},{
						'id': 1,
						'title': '大约在冬季 2019',
						'src': 'https://cn2.3days.cc/1577875712879260.jpeg',
						'actors': ['马思纯','霍建华', '魏大勋', '张瑶', '林柏宏', '文淇', '侯佩岑', '齐秦'],
						'desc': '　1991年齐秦狂飙演唱会上，北师大才女安然（马思纯 饰）和来自台北的摄影师齐啸（霍建华 饰）因缘相识，曲终人散后再度重逢的二人陷入热恋，然而不是勇敢就一定能拥有爱，不是所有再见都能再见！在漂泊岁月中，弄丢了挚爱的我们，是否还能安然无恙？没有我的日子里，你是否能保重自己？2019年，齐啸和安然能否重逢？',
						'url': 'https://jx.7639616.com/?url=https://cn7.kankia.com/hls/20200101/5c361debcd70cbd3cd118bc9d24186a4/1577874894/index.m3u8'
					},{
						'id': 2,
						'title': '大约在冬季 2019',
						'src': 'https://cn2.3days.cc/1577875712879260.jpeg',
						'actors': ['马思纯','霍建华', '魏大勋', '张瑶', '林柏宏', '文淇', '侯佩岑', '齐秦'],
						'desc': '　1991年齐秦狂飙演唱会上，北师大才女安然（马思纯 饰）和来自台北的摄影师齐啸（霍建华 饰）因缘相识，曲终人散后再度重逢的二人陷入热恋，然而不是勇敢就一定能拥有爱，不是所有再见都能再见！在漂泊岁月中，弄丢了挚爱的我们，是否还能安然无恙？没有我的日子里，你是否能保重自己？2019年，齐啸和安然能否重逢？',
						'url': 'https://jx.7639616.com/?url=https://cn7.kankia.com/hls/20200101/5c361debcd70cbd3cd118bc9d24186a4/1577874894/index.m3u8'
					},{
						'id': 3,
						'title': '大约在冬季 2019',
						'src': 'https://cn2.3days.cc/1577875712879260.jpeg',
						'actors': ['马思纯','霍建华', '魏大勋', '张瑶', '林柏宏', '文淇', '侯佩岑', '齐秦'],
						'desc': '　1991年齐秦狂飙演唱会上，北师大才女安然（马思纯 饰）和来自台北的摄影师齐啸（霍建华 饰）因缘相识，曲终人散后再度重逢的二人陷入热恋，然而不是勇敢就一定能拥有爱，不是所有再见都能再见！在漂泊岁月中，弄丢了挚爱的我们，是否还能安然无恙？没有我的日子里，你是否能保重自己？2019年，齐啸和安然能否重逢？',
						'url': 'https://jx.7639616.com/?url=https://cn7.kankia.com/hls/20200101/5c361debcd70cbd3cd118bc9d24186a4/1577874894/index.m3u8'
					},{
						'id': 4,
						'title': '大约在冬季 2019',
						'src': 'https://cn2.3days.cc/1577875712879260.jpeg',
						'actors': ['马思纯','霍建华', '魏大勋', '张瑶', '林柏宏', '文淇', '侯佩岑', '齐秦'],
						'desc': '　1991年齐秦狂飙演唱会上，北师大才女安然（马思纯 饰）和来自台北的摄影师齐啸（霍建华 饰）因缘相识，曲终人散后再度重逢的二人陷入热恋，然而不是勇敢就一定能拥有爱，不是所有再见都能再见！在漂泊岁月中，弄丢了挚爱的我们，是否还能安然无恙？没有我的日子里，你是否能保重自己？2019年，齐啸和安然能否重逢？',
						'url': 'https://jx.7639616.com/?url=https://cn7.kankia.com/hls/20200101/5c361debcd70cbd3cd118bc9d24186a4/1577874894/index.m3u8'
					},{
						'id': 5,
						'title': '大约在冬季 2019',
						'src': 'https://cn2.3days.cc/1577875712879260.jpeg',
						'actors': ['马思纯','霍建华', '魏大勋', '张瑶', '林柏宏', '文淇', '侯佩岑', '齐秦'],
						'desc': '　1991年齐秦狂飙演唱会上，北师大才女安然（马思纯 饰）和来自台北的摄影师齐啸（霍建华 饰）因缘相识，曲终人散后再度重逢的二人陷入热恋，然而不是勇敢就一定能拥有爱，不是所有再见都能再见！在漂泊岁月中，弄丢了挚爱的我们，是否还能安然无恙？没有我的日子里，你是否能保重自己？2019年，齐啸和安然能否重逢？',
						'url': 'https://jx.7639616.com/?url=https://cn7.kankia.com/hls/20200101/5c361debcd70cbd3cd118bc9d24186a4/1577874894/index.m3u8'
					}
				]
			
			}
		},
		onLoad() {

		},
		methods: {
			cardSwiper(e) {
				this.cardCur = e.detail.current
			},
			goDetail(){
				uni.navigateTo({
					url: '../detail/detail'
				})
			},
			goCategory(){
				uni.switchTab({
					url: '../category/category'
				})
			}
		}
	}
</script>

<style>
	@import url("./index.css");
</style>
