<template>
	<div class="mr-5">
		<img
			height="185"
			width="140"
			:src="avatarUrl"
			alt="Avatar"
			class="rounded"
		/>
		<div class="mt-4">
			<p class="player__role text-xs">{{ role }} /</p>
			<h6 class="tracking-tight font-bold">{{ handle }}</h6>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		role: String,
		handle: String,
		avatar: String
	},

	computed: {
		avatarUrl() {
			return require(`@/assets/images/${this.avatar}`)
		}
	}
}
</script>

<style lang="scss">
.player {
	&__role {
		color: var(--gray);
	}
}
</style>
