<template>
	<div
		:class="[
			'queue__container text-white',
			isMatchFound ? 'queue__status--found' : 'queue__status--searching'
		]"
	>
		<BackArrow />
		<div class="p-4">
			<Queue @matchFound="matchFound" />
		</div>
	</div>
</template>
<script>
import BackArrow from '@/components/navigation/BackArrow'
import Queue from '@/components/Queue'

export default {
	components: {
		BackArrow,
		Queue
	},

	data() {
		return {
			isMatchFound: false
		}
	},

	methods: {
		matchFound() {
			this.isMatchFound = true
		}
	}
}
</script>

<style lang="scss" scoped>
.queue {
	&__container {
		width: 350px;
		height: 635px;
	}
	&__status--searching {
		background-color: var(--background--blue--transparent);
		.navigation {
			background-color: var(--background--black);
		}
	}
	&__status--found {
		background-color: var(--background--black--transparent);
		.navivation {
			background-color: transparent;
		}
	}
}
</style>
