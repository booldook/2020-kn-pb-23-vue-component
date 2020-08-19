<template lang="pug">
	.prd-wrapper
		product(v-for="v in products" v-bind:key="v.id" v-bind:content="v")
</template>

<script>
import Product from '@/components/Product.vue'
import axios from 'axios'

export default {
	name: 'product-wrapper',
	props: ['search'],
	data() {
		return {
			products: []
		}
	},
	watch: {
		search: async function(newValue, oldValue) {
			try {
				var r = await axios.get('/json/products.json', {data: newValue});
				this.products = r.data.products;
			}
			catch(e) {
				console.log(e);
			}
		}
	},
	components: {
		'product': Product
	},
	methods: {
		
	}
}
</script>

<style lang="less">
	.prd-wrapper {display: flex; flex-wrap: wrap;}
</style>