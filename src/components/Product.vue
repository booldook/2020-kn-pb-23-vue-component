<template lang="pug">
	.prd
		img.w-100(src=`@/assets/img/blog-img-1.jpg`)
		.title 테스트상품
		.price $12.00
</template>

<script>
export default {

}
</script>

<style lang="less">
	@991: ~"(max-width: 991px)";
	@767: ~"(max-width: 767px)";
	@575: ~"(max-width: 575px)";
	.prd {
		flex: 25%; padding: 1%; width: 25%;
		@media @991 {
			flex: 33.3333%; width: 33.3333%;
		}
		@media @767 {
			flex: 50%; width: 50%; padding: 2%;
		}
		@media @575 {
			flex: 100%; width: 100%;
		}
	}
</style>