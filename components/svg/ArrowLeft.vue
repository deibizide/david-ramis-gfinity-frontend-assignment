<template>
	<div>
		<svg
			width="22"
			height="10"
			viewBox="0 0 22 10"
			fill="none"
			xmlns="http://www.w3.org/2000/svg"
		>
			<path d="M6 0L0 5L6 10V6H22V4H6V0Z" :fill="color" />
		</svg>
	</div>
</template>

<script>
export default {
	props: {
		color: {
			type: String,
			default: '#1B1B1B'
		}
	}
}
</script>

<style></style>
