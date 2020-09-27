<template>
	<div class="flex items-center py-5">
		<p class="w-1/5 text-xs mr-5">Lobby</p>
		<div class="w-1/5">
			<img
				:src="avatarUrl"
				class="rounded-full object-cover border-2 h-12 w-12 p-1"
				alt="player avatar"
			/>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		avatar: String
	},

	computed: {
		avatarUrl() {
			return require(`@/assets/images/${this.avatar}`)
		}
	}
}
</script>
