<template>
	<the-header title="Game APP"></the-header>
	<img alt="Vue logo" src="./assets/logo.png">
	<the-game></the-game>
</template>

<script>
	import TheHeader from './components/layouts/TheHeader.vue';
	import TheGame from './components/layouts/TheGame.vue';

	export default {
		name: 'App',
		components: {
			TheHeader,
			TheGame
		}
	}
</script>

<style>
	:root {
		--primary: #007791;
		--primary-hover: #43a8be;
	}
	* {
		box-sizing: border-box;
	}
	html {
		font-family: 'Jost', sans-serif;
	}
	body {
		margin: 0;
	}
	#app {
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
	}

</style>
