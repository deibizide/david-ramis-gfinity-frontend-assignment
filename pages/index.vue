<template>
	<div class="home flex flex-col justify-center items-center">
		<nuxt-link to="/lobby" tag="button">
			<span
				class="home__button tracking-wider text-white font-bold py-4 px-5 rounded"
			>
				Configure match
			</span>
		</nuxt-link>
	</div>
</template>
<script>
export default {}
</script>
<style lang="scss">
.home {
	height: calc(100vh - 105px);

	&__button {
		background-color: var(--background--blue--transparent);
		height: 20px;
	}
}
</style>
