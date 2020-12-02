<template>
	<base-card>
		<base-health :health="opponentHealth">Opponent Health</base-health>
	</base-card>
	<base-card>
		<base-health :health="playerHealth">Player Health</base-health>
	</base-card>

	<section class="container" v-if="! winner">

		<base-button 
			@click="playerAttack()"
			>ATTACK</base-button>
		<base-button 
			@click="specialAttack"
			:disabled="!canUseSpecialAttack"
			>SPECIAL ATTACK</base-button>

		<base-button>HEAL</base-button>
		<base-button>SURRENDER</base-button>

	</section>
	<section v-else>
		<base-card>
			<h2>Game over !</h2>
			<h2 v-if="winner === 'player'">You WON !</h2>
			<h2 v-else-if="winner === 'opponent'">You LOST !</h2>
			<h2 v-else>It's a DRAW !</h2>
		</base-card>
	</section>

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
		data() {
			return {
				opponentHealth: 100,
				playerHealth: 100,
				winner: null,
				attackCount: 0
			};
		},
		methods: {
			specialAttack() {
				this.attackCount = 0;
				this.playerAttack(10, 25);
			},
			playerAttack(min = 5, max = 11) {
				this.attackCount++;
				const attackValue = this.getRandomNumber(min, max);
				this.opponentHealth -= attackValue;
				this.opponentAttack();
			},
			opponentAttack() {
				const attackValue = this.getRandomNumber(6, 13);
				this.playerHealth -= attackValue;
			},
			getRandomNumber(min, max) {
				return Math.floor(Math.random() * (max - min))+ min;
			}
		},
		watch: {
			playerHealth(value) {
				if (value < 0 && this.opponentHealth < 0) {
					this.winner = 'draw';
				} else if (value <= 0){
					this.winner = 'opponent';
				}
			},
			opponentHealth(value) {
				if (value < 0 && this.playerHealth < 0) {
					this.winner = 'draw';
				} else if (value <= 0){
					this.winner = 'player';
				}
			},
		},
		computed: {
			canUseSpecialAttack() {
				return this.attackCount >= 3;
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