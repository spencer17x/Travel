<template>
	<div>
		<city-header></city-header>
		<city-search></city-search>
		<city-list :hotCities="hotCities" :cities="cities"></city-list>
		<city-alphabet :cities="cities"></city-alphabet>
	</div>
</template>

<script>
	import CityHeader from './components/Header'
	import CitySearch from './components/Search'
	import CityList from './components/List'
	import CityAlphabet from './components/Alphabet'
	import axios from 'axios'
	export default {
		name: 'City',
		components: {
			CityHeader,
			CitySearch,
			CityList,
			CityAlphabet
		},
		data () {
			return {
				hotCities: [],
				cities: {}
			}
		},
		methods: {
			getHomeInfo () {
				axios.get('/static/mock/city.json')
					.then(this.getHomeInfoSucc)
			},
			getHomeInfoSucc (res) {
				res = res.data
				if (res.ret && res.data) {
					const data = res.data
					this.hotCities = data.hotCities
					this.cities = data.cities
					// console.log(data);
					// console.log(data.hotCities);
					// this.city = data.city
					// this.swiperList = data.swiperList
					// this.iconList = data.iconList
					// this.recommendList = data.recommendList
					// this.weekendList = data.weekendList
					// console.log(res);
				}
			}
		},
		mounted () {
			this.getHomeInfo()
		}
	}
</script>

<style lang="stylus" scoped>
	
</style>