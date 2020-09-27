<template>
	<div class="flex">
		<div class="border border-black font-bold mr-3 status tracking-widest">
			<p class="m-0 mx-1">{{ status }}</p>
		</div>
		<GfPts />
	</div>
</template>

<script>
import GfPts from '@/components/svg/GfPts'

export default {
	components: { GfPts },
	data() {
		return {
			status: 'READY'
		}
	}
}
</script>

<style lang="scss">
.status {
	font-size: 10px;
}
</style>
