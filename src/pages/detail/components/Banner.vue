<template>
	<div>
		<div class="banner" @click="handleBannerClick">
			<img src="//img1.qunarzz.com/sight/p0/201408/14/dba7220ac844600c07a1af703f640935.jpg_600x330_ccb5f3fc.jpg" class="banner-img">
			<div class="banner-info">
				<div class="banner-title">
					杭州乐园(AAAA景区)
				</div>
				<div class="banner-number">
					<span class="iconfont banner-icon">&#xe692;</span>
					16
				</div>
			</div>
		</div>
		<common-gallery 
			:imgs="imgs" 
			v-show="showGallery" 
			@close="handleGalleryClose"
		></common-gallery>
	</div>
</template>

<script>
	import CommonGallery from 'common/gallery/Gallery'
	export default {
		name: 'DetailBanner',
		data () {
			return {
				showGallery: false,
				imgs: ['http://img1.qunarzz.com/sight/p0/201408/14/d6a9132a38b185cd25e6c7c5d65e0454.jpg_r_800x800_34ac98c3.jpg','http://img1.qunarzz.com/sight/p0/201408/14/a062e3db1854f204fe58feb100c69040.jpg_r_800x800_f010720c.jpg']
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
			CommonGallery
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