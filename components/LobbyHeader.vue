<template>
	<div class="lobby__header mb-5">
		<LobbyHeaderNavigation />

		<LineBreak />

		<div class="flex items-center justify-between mt-2">
			<h4 class="lobby__header__username font-bold tracking-tighter">
				{{ handle }}’s lobby
			</h4>
			<Lock />
		</div>

		<div class="flex justify-center font-bold lobby__header__game mt-2">
			<span>{{ game }}</span>
		</div>
	</div>
</template>

<script>
import Lock from '@/components/svg/Lock'
import LineBreak from '@/components/svg/LineBreak'
import LobbyHeaderNavigation from '@/components/navigation/LobbyHeaderNavigation'

export default {
	components: {
		Lock,
		LobbyHeaderNavigation,
		LineBreak
	},

	data() {
		return {
			handle: 'steveroesler',
			game: 'FIFA 19'
		}
	}
}
</script>

<style lang="scss">
.lobby__header {
	&__game {
		background-color: var(--black);
		color: var(--white);
		font-size: 10px;
		letter-spacing: 1.5px;
		width: 58px;
		height: 13px;
		border-radius: 0px 10px 10px 0px;
		font-family: 'bold';
	}

	&__username {
		font-family: 'bold';
		font-size: 36px;
	}
}
</style>
