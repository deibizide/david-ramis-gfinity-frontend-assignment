<template>
	<div class="play-now flex items-center justify-between text-sm">
		<p class="w-3/6 tracking-tighter font-bold ml-4">Play Now</p>
		<p class="w-2/6 tracking-tighter">
			{{ amount | formatNumber }} in Queue
		</p>
		<ArrowRight class="w-1/6 mr-4 flex justify-end" />
	</div>
</template>

<script>
import ArrowRight from '@/components/svg/ArrowRight'

export default {
	components: {
		ArrowRight
	},

	filters: {
		formatNumber(num) {
			return parseInt(num).toLocaleString()
		}
	},

	data() {
		return {
			amount: 4021
		}
	}
}
</script>

<style lang="scss">
.play-now {
	background-color: var(--background--blue);
	color: var(--white);
	height: 90px;
}

@media screen and (min-width: 451px) {
	.play-now {
		position: absolute;
		bottom: 0;
		left: 0;
		width: 100%;
	}
}
</style>
