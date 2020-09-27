<template>
	<div class="flex my-4">
		<div v-for="(player, index) in players" :key="index">
			<PlayerThumbnail
				:handle="player.handle"
				:role="player.role"
				:avatar="player.avatar"
			/>
		</div>

		<InvitePlayerThumbnail />
	</div>
</template>

<script>
import PlayerThumbnail from '@/components/PlayerThumbnail'
import InvitePlayerThumbnail from '@/components/InvitePlayerThumbnail'

export default {
	components: {
		PlayerThumbnail,
		InvitePlayerThumbnail
	},
	data() {
		return {
			players: [
				{
					role: 'Team Leader',
					handle: 'steveroesler',
					avatar: 'avatar-01.jpg'
				}
			]
		}
	}
}
</script>
