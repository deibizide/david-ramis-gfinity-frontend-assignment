<template>
	<div
		:class="[
			'queue__status flex justify-between p-5 items-center',
			isSearching ? 'queue__status--searching' : ''
		]"
	>
		<p class="w-3/5 font-bold text-sm">
			{{ statusText }}
			<span v-if="isSearching" class="queue__status__loader"></span>
		</p>
		<p class="w-1/5 flex justify-end text-sm">
			{{ statusTime }}
		</p>

		<div class="w-1/5 flex justify-end">
			<Close v-if="isSearching" />
			<ArrowRight v-else />
		</div>
	</div>
</template>

<script>
import ArrowRight from '@/components/svg/ArrowRight'
import Close from '@/components/svg/Close'

export default {
	components: {
		ArrowRight,
		Close
	},
	props: {
		isSearching: {
			type: Boolean,
			required: true
		}
	},

	data() {
		return {
			searchTime: '00:15',
			acceptTime: '00:17',

			countdownInterval: ''
		}
	},

	computed: {
		statusText() {
			return this.isSearching ? 'Searching' : 'Accept'
		},
		statusTime() {
			return this.isSearching ? this.searchTime : this.acceptTime
		}
	},

	watch: {
		'$router.path': {
			handler: 'startCountDown',
			immediate: true
		},

		isSearching: {
			handler(value) {
				if (value === false) clearInterval(this.countdownInterval)
			}
		}
	},

	methods: {
		startCountDown() {
			let minutes = 0
			let seconds = 14

			this.countdownInterval = setInterval(() => {
				if (seconds === 0 && minutes === 0) {
					this.$emit('searchComplete')
				}

				this.searchTime =
					'0' +
					minutes +
					':' +
					(seconds < 10 ? '0' + seconds : seconds)
				seconds--

				if (seconds === 0 && minutes !== 0) {
					minutes--
					seconds = 59
				}
			}, 1000)
		}
	}
}
</script>

<style lang="scss">
.queue {
	&__status {
		background-color: var(--background--blue);
		position: absolute;
		bottom: 25px;
		right: 0;
		height: 90px;
		width: 295px;

		&--searching {
			background-color: var(--background--black);
		}

		&__loader:after {
			overflow: hidden;
			display: inline-block;
			vertical-align: bottom;
			-webkit-animation: ellipsis steps(4, end) 1000ms infinite;
			animation: ellipsis steps(4, end) 1000ms infinite;
			content: '\2026';
			width: 0px;
		}
	}
}

@keyframes ellipsis {
	to {
		width: 20px;
	}
}

@-webkit-keyframes ellipsis {
	to {
		width: 20px;
	}
}
</style>
