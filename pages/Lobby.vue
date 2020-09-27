<template>
	<div class="lobby">
		<ImageHeader />
		<div class="mx-5">
			<LobbyHeader />
			<TeamOverview />
			<div class="mb-8">
				<TeamStatus />
			</div>
			<GameOptions />
		</div>
		<nuxt-link to="/queue">
			<PlayNow />
		</nuxt-link>
	</div>
</template>
<script>
// lobby components
import ImageHeader from '@/components/navigation/ImageHeader'
import TeamOverview from '@/components/TeamOverview'
import TeamStatus from '@/components/TeamStatus'
import GameOptions from '@/components/GameOptions'
import PlayNow from '@/components/PlayNow'
import LobbyHeader from '@/components/LobbyHeader'

export default {
	components: {
		ImageHeader,
		LobbyHeader,
		TeamOverview,
		TeamStatus,
		GameOptions,
		PlayNow
	}
}
</script>
