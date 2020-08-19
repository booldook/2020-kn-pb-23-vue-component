<template lang="pug">
	div#app.container
		nav-bar
		search-bar
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import SearchBar from '@/components/SearchBar.vue'

export default {
	name: 'app',
	components: {
		'nav-bar': NavBar,
		'search-bar': SearchBar,
	}
}
</script>

<style lang="less">
	
</style>