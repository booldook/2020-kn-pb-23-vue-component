<template lang="pug">
	.prd
		img.w-100(v-bind:src="require(`@/assets/img/${content.src}`)")
		.title {{content.title}}
		.price {{content.price}}
</template>

<script>
export default {
	name: 'product',
	props: ['content'],
}
</script>

<style lang="less">
	@991: ~"(max-width: 991px)";
	@767: ~"(max-width: 767px)";
	@575: ~"(max-width: 575px)";
	.prd {
		flex: 25% 0 0; padding: 1%; width: 25%;
		@media @991 {
			flex: 33.3333% 0 0; width: 33.3333%;
		}
		@media @767 {
			flex: 50% 0 0; width: 50%; padding: 2%;
		}
		@media @575 {
			flex: 100% 0 0; width: 100%;
		}
	}
</style>