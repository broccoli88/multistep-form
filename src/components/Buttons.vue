<script setup>
	import Button from "./Button.vue";
</script>

<template>
	<div class="button-container">
		<Button>
			<template v-slot:action>Previous Page</template>
		</Button>
		<Button>
			<template v-slot:action>Next Page</template>
		</Button>
	</div>
</template>

<style lang="scss" scoped>
	.button-container {
		display: flex;
	}
</style>
