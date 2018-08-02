<template>
	<div>
		<div class="search">
			<input 
				type="text" 
				placeholder="输入城市名或拼音" 
				class="search-input"
				v-model="keyword">
		</div>
		<div class="search-content" 
			 ref="search"
			 v-show="keyword">
			<ul>
				<li v-for="item of list" 
					class="search-item border-bottom"
					:key="item.id"
					>{{item.name}}</li>
				<li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
			</ul>
		</div>
	</div>
</template>

<script>
	import Bscroll from 'better-scroll'
	export default {
		name: 'CitySearch',
		data () {
			return {
				keyword: '',
				list: [],
				timer: null
			}
		},
		computed: {
			hasNoData () {
				return !this.list.length
			}
		},
		props: {
			cities: Object
		},
		watch: {
			keyword () {
				if (this.timer) {
					clearTimeout(this.timer)
				}
				if (!this.keyword) {
					this.list = []
					return
				}
				this.timer = setTimeout(() => {
					const result = []
					for (let i in this.cities) {
						this.cities[i].forEach((value) => {
							if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
								result.push(value)
							}
						})
					}
					this.list = result
				},100)
			}
		},
		mounted () {
			this.scroll = new Bscroll(this.$refs.search)
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.search
		height: .72rem
		background: $bgColor
		padding: 0 .1rem
		.search-input
			width: 100%
			height: .62rem
			text-align: center
			border-radius: .06rem
	.search-content
		position: absolute
		top: 1.58rem
		overflow: hidden
		background: #eee
		left: 0
		right: 0
		bottom: 0
		z-index: 1
		.search-item
			line-height: .62rem
			color: #666
			background: #fff
			padding-left: .2rem
			
</style>