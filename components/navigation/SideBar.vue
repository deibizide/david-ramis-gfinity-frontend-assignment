<template>
	<transition name="slide">
		<nav
			v-if="menuOpen"
			class="navbar__sidebar absolute right-0 bottom-0 w-screen flex justify-center items-center"
		>
			<div class="text-white text-center" @click="menuToggle">
				<nuxt-link class="block text-3xl tracking-tighter" to="/"
					>Home</nuxt-link
				>
				<nuxt-link class="block text-3xl tracking-tighter" to="/queue"
					>Queue</nuxt-link
				>
				<nuxt-link class="block text-3xl tracking-tighter" to="/lobby"
					>Lobby</nuxt-link
				>
			</div>
		</nav>
	</transition>
</template>

<script>
export default {
	props: {
		menuOpen: Boolean
	},

	methods: {
		menuToggle() {
			this.$emit('menuToggle')
		}
	}
}
</script>

<style lang="scss">
.navbar {
	/* ANIMATION */
	.open {
		background-color: var(--white);
		transform: rotate(45deg);
	}

	.open::after {
		transform: rotate(-90deg);
		background-color: var(--white);
	}

	&__sidebar {
		z-index: 10;
		background-color: var(--black);
		height: 100vh;
	}
	.slide-leave-active,
	.slide-enter-active {
		transition: 1s;
	}
	.slide-enter {
		transform: translate(100%, 0);
	}
	.slide-leave-to {
		transform: translate(100%, 0);
	}
}
</style>
