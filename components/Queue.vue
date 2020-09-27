<template>
	<div>
		<QueueHeader :is-searching="isSearching" />

		<QueueUser :avatar="avatar" />
		<QueueDetails :is-searching="isSearching" />

		<QueueStatus
			:is-searching="isSearching"
			@searchComplete="searchCompleted"
		/>
	</div>
</template>

<script>
import QueueHeader from '@/components/QueueHeader'
import QueueUser from '@/components/QueueUser'
import QueueDetails from '@/components/QueueDetails'
import QueueStatus from '@/components/QueueStatus'

export default {
	components: {
		QueueHeader,
		QueueUser,
		QueueDetails,
		QueueStatus
	},

	data() {
		return {
			isSearching: true,
			avatar: 'avatar-01.jpg'
		}
	},

	methods: {
		searchCompleted() {
			this.isSearching = false
			this.$emit('matchFound')
		}
	}
}
</script>

<style lang="scss">
.queue {
	&__container {
		background-color: var(--background--blue--transparent);
		width: 350px;
		height: 635px;
	}
}
</style>
