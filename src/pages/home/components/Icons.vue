<template>
	<div class="icons">
		<swiper>
			<swiper-slide v-for="(page,index) of pages" :key=index>
				<div 
					class="icon"
					v-for="item of page"
					:key="item.id"
					>
					<div class="icon-img">
						<img class="icon-img-content" :src="item.imgUrl">
					</div>
					<p class="icon-desc">{{item.desc}}</p>
				</div>
			</swiper-slide>
		</swiper>
	</div>
</template>

<script>
	export default {
		name: 'HomeIcons',
		data () {
			return {
				iconList: [{
					id: '0001',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
					desc: '景点门票'
				},{
					id: '0002',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
					desc: '一日游'
				},{
					id: '0003',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
					desc: '杭州必游'
				},{
					id: '0004',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/75/eca3ce656c886502.png',
					desc: '漂游'
				},{
					id: '0005',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
					desc: '夏日玩水'
				},{
					id: '0006',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/17/99402a22ce4af302.png',
					desc: '西湖'
				},{
					id: '0007',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
					desc: '宋城千古情'
				},{
					id: '0008',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/95/8d02011d149bdb02.png',
					desc: '汽车票'
				},{
					id: '0009',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/75/eca3ce656c886502.png',
					desc: '千岛湖'
				},{
					id: '0010',
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
					desc: '全部玩乐'
				}]
			}
		},
		computed: {
			pages () {
				const pages = []
				this.iconList.forEach((item,index) => {
					const page = Math.floor(index/8)
					if (!pages[page]) {
						pages[page] = []
					}
					pages[page].push(item)
				})
				return pages
			}
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	@import '~styles/mixins.styl'
	.icons >>> .swiper-container
		height: 0
		padding-bottom: 50%
	.icon
		overflow: hidden
		width: 25%
		float: left
		padding-bottom: 25%
		position: relative
		height: 0
		.icon-desc
			position: absolute
			left: 0
			bottom: 0
			right: 0
			height: .44rem
			line-height: .44rem
			color: $darkTextColor
			text-align: center
			ellipsis()
		.icon-img
			position: absolute
			left: 0
			right: 0
			top: 0
			bottom: .44rem
			padding: .1rem
			box-sizing: border-box
			.icon-img-content
				display: block
				height: 100%
				margin: 0 auto
</style>