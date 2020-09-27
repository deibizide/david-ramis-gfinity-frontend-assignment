<template>
	<div class="flex items-center py-5 text-xs">
		<p class="w-1/5 mr-5"><HorizontalRule /></p>
		<p v-if="isSearching" class="w-2/5">
			<span class="font-extrabold">{{ queueAmount | formatNumber }}</span>
			in Queue
		</p>
		<p v-else class="w-4/5 tracking-tighter">
			By tapping accept, you agree to play a match that may last for up to
			30 minutes.
		</p>
	</div>
</template>
<script>
import HorizontalRule from '@/components/svg/HorizontalRule'

export default {
	components: {
		HorizontalRule
	},

	filters: {
		formatNumber(num) {
			return parseInt(num).toLocaleString()
		}
	},
	props: {
		isSearching: {
			type: Boolean,
			required: true
		}
	},

	data() {
		return {
			queueAmount: 4021
		}
	}
}
</script>
