<template>
	<div class="flex items-center border-box">
		<nuxt-link to="/queue">
			<ArrowLeft />
		</nuxt-link>
		<p class="font-extrabold my-3 ml-6">Matchmaking Lobby</p>
	</div>
</template>
<script>
import ArrowLeft from '@/components/svg/ArrowLeft'

export default {
	components: {
		ArrowLeft
	}
}
</script>
