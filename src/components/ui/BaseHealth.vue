<template>
	<h2>
		<slot></slot>
	</h2>
	<div class="health">
		<div class="energy" :style="healthBar">
		</div>
	</div>
</template>

<script>
	export default {
		props: ['health'],
		computed: {
			healthBar() {
				if (this.health < 0) {
					return {
						width: 0 + '%',
					}					
				} else if (this.health < 15) {
					return {
						width: this.health + '%',
						backgroundColor: '#e00000eb',
					}
				} else {
					return {
						width: this.health + '%',
					}
				}

			}
		}
	}
</script>

<style scoped>
	.health {
		height: 40px;
		margin: 10px 0;
		border: 1px solid rgba(39, 39, 39, 0.66);
		border-radius: 5px;
	}
	.energy {
		height: 100%;
		background-color: #41b883;
		border-radius: 2px;
	}
</style>