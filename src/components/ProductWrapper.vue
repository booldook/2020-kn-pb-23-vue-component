<template lang="pug">
	.prd-wrapper
		product
		product
		product
		product
</template>

<script>
import Product from '@/components/Product.vue'

export default {
	name: 'product-wrapper',
	components: {
		'product': Product
	}
}
</script>

<style lang="less">

</style>