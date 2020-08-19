<template lang="pug">
	form(v-on:submit.prevent='onSubmit' id='searchForm' name='searchForm')
		input.form-control(v-model='search' type="text" placeholder="상품 검색어를 입력하세요." autofocus)
		i.fa.fa-times-circle(v-show='search.length' v-on:click='onReset')
</template>

<script>
export default {
	name: 'search-bar',
	data() {
		return {
			search: ''
		}
	},
	methods: {
		onSubmit() {
			// 자식이 부모에게 데이터를 전달하려면 이벤트형식으로 전달해야 한다.
			this.$emit('@submit', this.search);
		},
		onReset() {
			this.search = '';
			this.$emit('@submit', this.search);
		}
	}
}
</script>

<style lang="less">
	.pointer {cursor: pointer;}
	#searchForm {
		position: relative;
		i {position: absolute; right: 1rem; top: 0.625rem; font-size: 1.25rem; .pointer();}
	}
</style>