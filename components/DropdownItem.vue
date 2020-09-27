<template>
	<div class="flex my-1 py-3">
		<p class="w-3/6 font-bold">
			{{ category.title }}
		</p>
		<div class="w-2/6">
			<p class="font-light">
				{{ selectedGameOptions[categoryIndex][0] }}
			</p>
			<div v-for="(option, index) in category.option" :key="index">
				<transition name="slide">
					<ul v-show="showMenu">
						<li
							class="text-xs font-light mt-2"
							@click="
								handleSelectedOption(
									categoryIndex,
									option.title
									// eslint-disable-next-line prettier/prettier
								)
							"
						>
							{{ option.title }}
						</li>
					</ul>
				</transition>
			</div>
		</div>
		<div class="w-1/6 flex justify-end">
			<transition name="rotate">
				<button
					class="dropdown__toggle p-1 h-5"
					@click="toggleDropdown(categoryIndex)"
				>
					<ChevronDown />
				</button>
			</transition>
		</div>
	</div>
</template>

<script>
import ChevronDown from '@/components/svg/ChevronDown'

export default {
	components: {
		ChevronDown
	},
	props: {
		showMenu: Boolean,
		category: Object,
		categoryIndex: Number,
		selectedGameOptions: Array
	},

	methods: {
		toggleDropdown(i) {
			this.$emit('toggleDropdown', i)
		},
		handleSelectedOption(i, option) {
			this.$emit('handleSelectedOption', i, option)
		}
	}
}
</script>

<style lang="scss">
.dropdown {
	font-size: 0.85rem;

	&__toggle:focus {
		outline: 5px auto var(--border--color--blue);
	}

	.slide-enter-active {
		transition-duration: 0.3s;
		transition-timing-function: ease-in;
	}

	.slide-leave-active {
		transition-duration: 0.3s;
		transition-timing-function: cubic-bezier(0, 1, 0.5, 1);
	}

	.slide-enter-to,
	.slide-leave {
		max-height: 100px;
		overflow: hidden;
	}

	.slide-enter,
	.slide-leave-to {
		overflow: hidden;
		max-height: 0;
	}
}
</style>
