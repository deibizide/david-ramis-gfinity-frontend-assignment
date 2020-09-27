<template>
	<div class="dropdown tracking-tighter">
		<div v-for="(category, i) in gameOptions" :key="i">
			<LineBreak />
			<DropdownItem
				:show-menu="showMenu[i]"
				:selected-game-options="selectedGameOptions"
				:category="category"
				:category-index="i"
				@toggleDropdown="toggleDropdown"
				@handleSelectedOption="handleSelectedOption"
			/>
		</div>
	</div>
</template>

<script>
import LineBreak from '@/components/svg/LineBreak'
import DropdownItem from '@/components/DropdownItem'

export default {
	components: {
		LineBreak,
		DropdownItem
	},
	data() {
		return {
			showMenu: { '0': false, '1': false, '2': false },
			gameOptions: [
				{
					title: 'Type',
					option: [
						{ title: 'Competitive', isSelected: true },
						{ title: 'Friendly Game', isSelected: false },
						{ title: 'Exhibition', isSelected: false }
					]
				},
				{
					title: 'Game Mode',
					option: [
						{ title: 'Squad Battles', isSelected: true },
						{ title: 'Spectator', isSelected: false },
						{ title: 'Survival', isSelected: false }
					]
				},
				{
					title: 'Lobby Status',
					option: [
						{ title: 'Invite Only', isSelected: true },
						{ title: 'Public', isSelected: false }
					]
				}
			]
		}
	},
	computed: {
		selectedGameOptions() {
			return this.gameOptions.map(type =>
				type.option
					.filter(res => res.isSelected)
					.map(item => item.title)
			)
		}
	},
	methods: {
		toggleDropdown(i) {
			this.showMenu[i] = !this.showMenu[i]
		},
		handleSelectedOption(i, selectedOption) {
			this.gameOptions[i].option.forEach(elem => {
				elem.isSelected = false
				if (elem.title === selectedOption) {
					elem.isSelected = true
				}
			})
		}
	}
}
</script>
