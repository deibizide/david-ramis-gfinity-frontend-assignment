<template>
	<nav class="navbar bg-transparent flex items-center justify-between">
		<div class="navbar__logo flex items-center justify-center">
			<nuxt-link to="/"> <Logo /> </nuxt-link>
		</div>

		<div class="flex mr-2">
			<h4 class="font-bold">FIFA 19</h4>
			<div class="z-20" @click="menuToggle">
				<div
					class="mx-6 m-2 navbar__icon"
					:class="{ open: menuOpen }"
				></div>
			</div>
		</div>

		<SideBar :menu-open="menuOpen" @menuToggle="menuToggle" />
	</nav>
</template>

<script>
import Logo from '@/components/svg/Logo'
import SideBar from '@/components/navigation/SideBar'

export default {
	components: {
		Logo,
		SideBar
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
	&__logo {
		background-color: var(--background--black);
		width: 105px;
		height: 105px;
	}

	&__icon {
		z-index: 11;
		width: 20px;
		height: 3px;
		background: var(--background--black);
		transition: all 0.5s ease-in-out;
	}
	&__icon::after {
		content: '';
		position: absolute;
		width: 20px;
		height: 3px;
		background: var(--background--black);
		transition: all 0.5s ease-in-out;
	}

	&__icon::after {
		transform: translateY(10px);
	}
}
</style>
