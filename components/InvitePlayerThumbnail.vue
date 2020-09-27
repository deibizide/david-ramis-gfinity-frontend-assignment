<template>
	<div>
		<div class="thumbnail__img-placeholder rounded"></div>
		<div class="mt-4">
			<p class="thumbnail__text text-xs">Team Player /</p>
			<div class="flex items-center">
				<h6 class="tracking-tight font-bold mr-4">
					Invite Player
				</h6>
				<ChevronLeft />
			</div>
		</div>
	</div>
</template>

<script>
import ChevronLeft from '@/components/svg/ChevronLeft'

export default {
	components: { ChevronLeft }
}
</script>

<style lang="scss">
.thumbnail {
	&__text {
		color: var(--gray);
	}

	&__img-placeholder {
		height: 187px;
		width: 140px;
		border: 1px solid var(--border--color--gray);
	}
}
</style>
