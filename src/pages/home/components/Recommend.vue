<template>
	<div>
		<div class="title">热销推荐</div>
		<ul>
			<router-link 
				tag="li" 
				:to="'/detail/' + item.id"
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
			</router-link>
		</ul>
	</div>
</template>

<script>
	export default {
		name: 'HomeRecommend',
		props: {
			recommendList: Array
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