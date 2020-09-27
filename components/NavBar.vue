<template>
	<nav class="navbar flex items-center justify-between ">
		<div class="navbar__logo flex items-center justify-center">
			<nuxt-link to="/"> <Logo /> </nuxt-link>
		</div>
		<div class="flex navbar__burger-wrapper">
			<h4 class="font-bold">FIFA 19</h4>
			<div
				class="mx-6 m-2 navbar__burger-menu"
				:class="{ open: menuOpen }"
				@click="menuToggle"
			></div>
		</div>
		<transition name="slide">
			<div
				v-if="menuOpen"
				class="navbar__side-container absolute right-0 w-full"
			>
				<ul
					class="flex flex-col navbar__side-container--list text-5xl text-center"
					@click="menuToggle"
				>
					<nuxt-link to="/">Home</nuxt-link>
					<nuxt-link to="/queue">Queue</nuxt-link>
					<nuxt-link to="/lobby">Lobby</nuxt-link>
				</ul>
			</div>
		</transition>
	</nav>
</template>

<script>
import Logo from '@/components/svg/Logo'
export default {
	components: {
		Logo
	},
	data() {
		return {
			menuOpen: false
		}
	},

	methods: {
		menuToggle() {
			this.menuOpen = !this.menuOpen
		}
	}
}
</script>

<style lang="scss">
.navbar {
	background-color: transparent;

	&__logo {
		background-color: var(--background--black);
		width: 105px;
		height: 105px;
	}

	&__burger-wrapper {
		cursor: pointer;
		padding: 10px 0px;
		font-family: 'bold';
	}

	&__burger-menu {
		z-index: 11;
		width: 20px;
		height: 3px;
		background: var(--background--black);
		transition: all 0.5s ease-in-out;
	}
	&__burger-menu::after {
		content: '';
		position: absolute;
		width: 20px;
		height: 3px;
		background: var(--background--black);
		transition: all 0.5s ease-in-out;
	}

	&__burger-menu::after {
		transform: translateY(10px);
	}
	/* ANIMATION */
	.open {
		background-color: var(--white);
		transform: rotate(45deg);
	}

	.open::after {
		transform: rotate(-90deg);
		background-color: var(--white);
	}

	&__side-container {
		z-index: 10;
		background-color: var(--black);
		height: 188vh;
		&--list {
			color: var(--white);
			position: absolute;
			bottom: 300px;
			right: 120px;
		}
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
