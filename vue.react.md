# Vue, React에서 사용하는 기술(모듈)
## 저장소(전역변수)
	1. vue --> vuex
	2. react --> redux
## ServerSideRendering
	1. vue -> nuxt
	2. react -> next

## xxxx.vue 의 구조
```js
export default {
	name: '....',
	data() {
		// 전역변수 등록
		return {
			a: '',
			b: ''
		}
	},
	methods: {
		onSubmit() {

		}
	},
	components: {
		'태그명': NavBar,
		'태그명': SearchBar,
	},
	// 내 부모가 <나의태그명 v-bind:전달할변수명="값"> 전달
	props: ['전달받은 변수명', '전달받은 변수명2'],
	watch: {
		감시할변수명: function(newValue, oldValue) {
			// 감시하는 변수가 변하면 본 함수가 실행된다.
		}
	},
	computed: {
		함수등록
	},
	created() {
		// vue가 생성될 때(화면에 붙기전) 호출되는 메서드
	}, 
	mounted() {
		// vue가 화면에 붙으면 호출되는 메서드
	}, 
	beforeUpdate() {
		// 화면(view)이 갱신되기 전에 실행되는 메서드
	}, 
	updated() {
		// 화면(view)이 갱신되고 난 후에 실행되는 메서드
	}, 
	beforeDestroy() {
		// vue가 삭제되기 직전엔 발생하는 이벤트
	}
}
```

## vue의 부모와 자식이 변수를 전달하는 방식
1. 부모 -> 자식 (부모는 자식에게 bind -> props 전달)
- 부모
```html
<child v-bind:변수명="값">
```
- 자식
```js
export default {
	props: ['변수명']
}
```
2. 자식 -> 부모 (이벤트를 통해서 전달)
- 자식
```js
export default {
	methods: {
		onSubmit() {
			this.$emit('@submit', '값')
		}
	}
}
```
- 부모
```html
<자식태그 v-on:@submit='onSubmit'>
```
```js
export default {
	methods: {
		onSubmit(value) {
			this.query = value;
		}
	}
}
```