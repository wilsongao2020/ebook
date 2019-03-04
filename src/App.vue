<template>
	<div id="app">
		<div class="nav">
			<router-link to="/">Home</router-link> |
			<router-link to="/about">About</router-link>
		</div>
		<router-view/>
	</div>

</template>

<script type="text/javascript">
import { mapGetters } from 'vuex'
export default {
	computed: {
		...mapGetters([
			'test',
      	])
	},
	mounted() {
		this.$store.dispatch('setTest', 15).then(() => {
			console.log(this.test)
		})
	}
}
document.addEventListener('DOMContentLoaded', () => {
	const html = document.querySelector('html')
	let fontSize = window.innerWidth / 10
	fontSize = fontSize > 50 ? 50 : fontSize
	html.style.fontSize = fontSize + 'px'
})
</script>

<style lang="scss" scoped>
@import "./assets/styles/global";
.text {
	font-family: "Days One";
	font-size: px2rem(20);
}
</style>
