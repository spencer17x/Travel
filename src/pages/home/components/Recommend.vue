<template>
	<div>
		<div class="title">热销推荐</div>
		<ul>
			<li 
				class="item border-bottom" 
				v-for="item of recommendList"
				:key="item.id"
				>
				<img :src="item.imgUrl" class="item-img">
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
	export default {
		name: 'HomeRecommend',
		data () {
			return {
				recommendList: [{
					id: '0001',
					imgUrl: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
					title: '上海迪士尼乐园',
					desc: '云曼温泉能看秀的温泉'
				},{
					id: '0002',
					imgUrl: 'http://img1.qunarzz.com/sight/p0/201401/06/3fbbddda915cb7637439d484440d36be.jpg_200x200_a54e87dd.jpg',
					title: '杭州云曼温泉',
					desc: '云曼温泉能看秀的温泉'
				},{
					id: '0003',
					imgUrl: 'http://img1.qunarzz.com/sight/p0/201408/14/dba7220ac844600c07a1af703f640935.jpg_200x200_a84b7d79.jpg',
					title: '杭州乐园',
					desc: '云曼温泉能看秀的温泉'
				},{
					id: '0004',
					imgUrl: 'http://img1.qunarzz.com/sight/p0/1706/45/456c4be6ba4fa604a3.img.jpg_200x200_81d9a0be.jpg',
					title: '杭州浪浪浪水公园',
					desc: '云曼温泉能看秀的温泉'
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
	.item
		display: flex
		height: 1.9rem
		.item-img
			width: 1.7rem
			height: 1.7rem
			padding: .1rem
		.item-info
			flex: 1
			min-width: 0
			padding: .1rem
			.item-title
				line-height: .54rem
				font-size: .32rem
				ellipsis()
			.item-desc
				line-height: .44rem
				color: #ccc
				ellipsis()
			.item-button
				line-height: .44rem
				margin-top: .1rem
				background: #ff9300
				padding: 0 .2rem
				color: #fff
				border-radius: .06rem
</style>