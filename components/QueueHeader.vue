<template>
	<div class="mb-5">
		<h6 class="font-bold my-5">Matchmaking Lobby</h6>
		<h1 class="font-bold text-5xl tracking-tighter leading-none mb-5">
			{{ headline }}
		</h1>
		<p class="tracking-tight">
			{{ text }}
		</p>
	</div>
</template>

<script>
export default {
	props: {
		isSearching: Boolean
	},

	computed: {
		headline() {
			return this.isSearching
				? 'Searching for compatible opponents'
				: 'A match has been found for you!'
		},

		text() {
			return this.isSearching
				? `We're searching our database of players to pair you with an opponent
			of similar skill`
				: `We've found a compatible oppponent for you to play Squad Battles
			with in FIFA 19`
		}
	}
}
</script>
