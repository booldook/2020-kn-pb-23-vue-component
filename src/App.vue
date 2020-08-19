<template lang="pug">
	div#app.container
		nav-bar
		search-bar(v-on:@submit="onSubmit")
		product-wrapper(v-show="search.length")
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import SearchBar from '@/components/SearchBar.vue'
import ProductWrapper from '@/components/ProductWrapper.vue'

export default {
	name: 'app',
	data() {
		return {
			search: ''
		}
	},
	components: {
		'nav-bar': NavBar,
		'search-bar': SearchBar,
		'product-wrapper': ProductWrapper,
	},
	methods: {
		onSubmit(value) {
			this.search = value;
		}
	}
}
</script>

<style lang="less">
	
</style>