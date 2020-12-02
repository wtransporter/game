<template>
	<button>
		<slot></slot>
	</button>
</template>

<script>
	export default {

	}
</script>

<style scoped>
	button {
		font-family: inherit;
		font-size: 16px;
		background-color: var(--primary);
		border: 1px solid var(--primary-hover);
		border-radius: 5px;
		padding: 10px 32px;
		margin: 20px;
		color: white;
		cursor: pointer;
		outline-color: var(--primary-hover);
		min-width: 200px;
	}
	button:hover {
		background-color: var(--primary-hover);
	}
	button:disabled {
		background-color: #ccc;
		border-color: #ccc;
		box-shadow: none;
		color: #3f3f3f;
		cursor: not-allowed;
	}
</style>