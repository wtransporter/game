<template>
	<base-card>
		<base-health>Opponent Health</base-health>
	</base-card>
	<base-card>
		<base-health>Player Health</base-health>
	</base-card>
	<base-card>
		<button @click="playerAttack">Attack</button>
	</base-card>
</template>

<script>
	import BaseCard from '../ui/BaseCard.vue';
	import BaseHealth from '../ui/BaseHealth.vue';

	export default {
		components: {
			BaseCard,
			BaseHealth
		},
	}
</script>