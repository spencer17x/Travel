<template>
	<div>
		<div class="title">周末去哪儿</div>
		<ul>
			<li 
				class="item border-bottom" 
				v-for="item of recommendList"
				:key="item.id"
				>
				<div class="item-img-wrapper">
					<img :src="item.imgUrl" class="item-img">
				</div>
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
	export default {
		name: 'HomeWeekend',
		data () {
			return {
				recommendList: [{
					id: '0001',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
					title: '杭州必游TOP10',
					desc: '杭州，前世今生与你有一场美丽约会'
				},{
					id: '0002',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1505/9f/7d45cc38259e0.jpg_r_640x214_156f4299.jpg',
					title: '承载杭城的历史之地',
					desc: '饱经沧桑的地方诉述着这座城的段段衷肠'
				},{
					id: '0003',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1507/61/a7564da6033311.jpg_r_640x214_cc570e76.jpg',
					title: '激情漂流，嗨翻夏日',
					desc: '漂起来，展现你的“湿身”诱惑'
				},{
					id: '0004',
					imgUrl: 'http://img1.qunarzz.com/sight/source/1505/ae/4fe23c6b6679e2.jpg_r_640x214_368a18d8.jpg',
					title: '美仑美奂的演出',
					desc: '一座有故事的城，天天有“戏”在上演'
				},{
					id: '0005',
					imgUrl: 'http://img1.qunarzz.com/sight/p0/201301/15/ac836d7b5423301093835fbb.jpg_200x200_504e2672.jpg',
					title: '千岛湖王子谷漂流',
					desc: '云曼温泉能看秀的温泉'
				}]
			}
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/mixins.styl'
	.title
		line-height: .8rem
		background: #eee
		text-indent: .2rem
		margin-top: .2rem
	.item-img-wrapper
		padding-bottom: 36.9%
		overflow: hidden
		height: 0
		.item-img
			width: 100%
	.item-info
		padding: .1rem
		.item-title
			line-height: .54rem
			font-size: .32rem
			ellipsis()
		.item-desc
			line-height: .44rem
			color: #ccc
			ellipsis()
</style>