<template>
	<div class="list" ref="wrapper">
		<div>
			<div class="area">
				<div class="titile border-topbottom">当前城市</div>
				<div class="button-list">
					<div class="button-wrapper">
						<div class="button">{{this.$store.state.city}}</div>
					</div>
				</div>
			</div>
			<div class="area">
				<div class="titile border-topbottom">热门城市</div>
				<div class="button-list">
					<div 
						class="button-wrapper" 
						v-for="item of hotCities"
						:key="item.id"
						@click="handleCityClick(item.name)"
					>
						<div class="button">{{item.name}}</div>
					</div>
				</div>
			</div>
			<div class="area" 
				v-for="(city,key,index) of cities" 
				:key="index"
				:ref="key"	
			>
				<div class="titile border-topbottom">{{key}}</div>
				<div class="item-list">
					<div 
						class="item border-bottom" 
						v-for="alphabetCity of city"
						:key="alphabetCity.id"
						@click="handleCityClick(alphabetCity.name)"	
					>{{alphabetCity.name}}</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import Bscroll from 'better-scroll'
	export default {
		name: 'CityList',
		props: {
			hotCities: Array,
			cities: Object,
			letter: String
		},
		methods: {
			handleCityClick (city) {
				this.$store.commit('changeCity',city)
				this.$router.push('/')
			}
		},
		watch: {
			letter () {
				if (this.letter) {
					const element = this.$refs[this.letter][0];
					this.scroll.scrollToElement(element)
				}
			}
		},
		mounted () {
			this.scroll = new Bscroll(this.$refs.wrapper)
		}
	}
</script>

<style lang="stylus" scoped>
	@import '~styles/varibles.styl'
	.border-topbottom
		&:before
			border-color: #ccc
		&:after
			border-color: #ccc
	.border-bottom
		&:before
			border-color: #ccc
	.list 
		position: absolute
		top: 1.58rem
		left: 0
		right: 0
		bottom: 0
		overflow: hidden
		.titile 
			line-height: .54rem
			background: #eee
			padding-left: .26rem
			color: #666
			font-size: .26rem
		.button-list
			padding: .1rem .6rem .1rem .1rem
			overflow: hidden
			.button-wrapper
				width: 33.33%
				float: left
				.button
					padding: .1rem 0
					border-radius: .3px
					text-align: center
					margin: .1rem
					border: .02rem solid #ccc 
		.item-list
			.item
				line-height: .76rem
				padding-left: .2rem
</style>