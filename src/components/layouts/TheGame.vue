<template>
	<base-card>
		<base-health>Opponent Health</base-health>
	</base-card>
	<base-card>
		<base-health>Player Health</base-health>
	</base-card>

	<div class="container">

			<base-button @click="playerAttack">ATTACK</base-button>
			<base-button @click="playerAttack">SPECIAL ATTACK</base-button>

			<base-button @click="playerAttack">HEAL</base-button>
			<base-button @click="playerAttack">SURRENDER</base-button>

	</div>

</template>

<script>
	import BaseCard from '../ui/BaseCard.vue';
	import BaseHealth from '../ui/BaseHealth.vue';
	import BaseButton from '../ui/BaseButton.vue';

	export default {
		components: {
			BaseCard,
			BaseHealth,
			BaseButton
		},

		methods: {
			playerAttack() {

			}
		}
	}
</script>

<style scoped>
	.container {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		align-items: center;
		justify-content: center;
		max-width: 640px;
		margin: auto;
	}
</style>