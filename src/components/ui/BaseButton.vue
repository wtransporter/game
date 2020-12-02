<template>
	<button>
		<slot></slot>
	</button>
</template>

<style scoped>
	button {
		font-family: inherit;
		font-size: 16px;
		background-color: green;
		border: 1px solid green;
		border-radius: 5px;
		padding: 10px 32px;
		margin: 20px;
		color: white;
		cursor: pointer;
		outline-color: rgb(45, 153, 45);
		min-width: 200px;
	}
	button:hover {
		background-color: rgb(45, 153, 45);
	}
</style>