<template>
	<div>
		<div class="banner" @click="handleBannerClick">
			<img :src="bannerImg" class="banner-img">
			<div class="banner-info">
				<div class="banner-title">
					{{this.sightName}}
				</div>
				<div class="banner-number">
					<span class="iconfont banner-icon">&#xe692;</span>
					{{this.bannerImgs.length}}
				</div>
			</div>
		</div>
		<fade-animation>
			<common-gallery 
				:imgs="bannerImgs" 
				v-show="showGallery" 
				@close="handleGalleryClose"
			></common-gallery>
		</fade-animation>
	</div>
</template>

<script>
	import CommonGallery from 'common/gallery/Gallery'
	import FadeAnimation from 'common/fade/FadeAnimation'
	export default {
		name: 'DetailBanner',
		props: {
			sightName: String,
			bannerImg: String,
			bannerImgs: Array
		},
		data () {
			return {
				showGallery: false
			}
		},
		methods: {
			handleBannerClick () {
				this.showGallery = true
			},
			handleGalleryClose () {
				this.showGallery = false
			}
		},
		components: {
			CommonGallery,
			FadeAnimation
		}
	}
</script>

<style lang="stylus" scoped>
	.banner
		overflow: hidden
		height: 0
		padding-bottom: 54%
		position: relative
		color: #fff
		.banner-img
			width: 100%
		.banner-info
			display: flex
			position: absolute
			padding-bottom: .16rem
			left: 0
			right: 0
			bottom: 0
			line-height: .4rem
			background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
			.banner-title
				flex: 1
				font-size: .32rem
				padding: 0 .2rem
			.banner-number
				padding: 0 .14rem
				line-height: .32rem
				height: .32rem
				border-radius: .2rem
				font-size: 24rem
				background: rgba(0,0,0,.8)
				font-size: .24rem
				margin-top: .05rem
				.banner-icon
					font-size: .24rem
</style>