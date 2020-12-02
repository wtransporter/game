<template>
	<h2>
		<slot></slot>
	</h2>
	<div class="health">
		<div class="energy">
		</div>
	</div>
</template>

<style scoped>
	.health {
		height: 40px;
		margin: 10px 0;
		border: 1px solid rgba(39, 39, 39, 0.86);
	}
	.energy {
		height: 100%;
		background-color: green;
	}
</style>