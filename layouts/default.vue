<template>
	<div id="app" :class="['wrapper', pageBackgroundClass]">
		<NavBar />
		<nuxt />
	</div>
</template>

<script>
import NavBar from '@/components/navigation/NavBar'

export default {
	components: {
		NavBar
	},

	data() {
		return {
			pageBackgroundClass: ''
		}
	},

	watch: {
		'$route.path': {
			handler: 'assignBackgroundImage',
			deep: true,
			immediate: true
		}
	},

	methods: {
		assignBackgroundImage() {
			if (this.$router.history.current.name === 'queue') {
				this.pageBackgroundClass = 'wrapper__queue'
				return
			}

			this.pageBackgroundClass = ''
		}
	}
}
</script>

<style lang="scss" scoped>
.wrapper {
	background-color: var(--background--gray);
	min-height: 100vh;

	&__queue {
		background: url('~@/assets/images/fifa19-ronaldo.png'),
			url('~@/assets/images/shape-512w.png');
		background-size: 90%, 100%;
		background-position: 40px 75px, 0px -10px;

		background-repeat: no-repeat;
		background-color: var(--background--gray);
	}
}

@media screen and (min-width: 451px) {
	.wrapper__queue {
		background-size: 100%, 100%;
	}
}
</style>
