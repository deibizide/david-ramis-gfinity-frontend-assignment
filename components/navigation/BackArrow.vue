<template>
	<nav class="navigation flex justify-center items-center">
		<nuxt-link to="/lobby">
			<ArrowLeft :color="arrowColor" />
		</nuxt-link>
	</nav>
</template>
<script>
import ArrowLeft from '@/components/svg/ArrowLeft'

export default {
	components: {
		ArrowLeft
	},

	data() {
		return {
			arrowColor: '#ffffff'
		}
	}
}
</script>

<style lang="scss">
.navigation {
	height: 105px;
	width: 105px;
}
</style>
