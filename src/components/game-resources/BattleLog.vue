<template>
	<h2>
		<slot></slot>	
	</h2>
	<ul>
		<log-list></log-list>
	</ul>
</template>

<script>
	import LogList from "./LogList.vue";
	export default {
		components: {
			LogList,
		},
	}
</script>

<style scoped>
	ul {
		list-style: none;
		padding: 0;
	}
</style>