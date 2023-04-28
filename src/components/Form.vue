<script setup>
	const emit = defineEmits(["submitForm"]);
	const emitSubmit = () => [emit("submitForm")];
</script>

<template>
	<form action="" class="form" @submit.prevent="emitSubmit">
		<fieldset class="fieldset">
			<legend class="legend">
				<slot name="legend"></slot>
			</legend>
			<slot name="inputs"></slot>
		</fieldset>
	</form>
</template>

<style lang="scss" scoped>
	.form {
		grid-area: form;
	}

	.fieldset {
		border: none;
		padding: 2rem;

		.legend {
			font-size: 3rem;
			font-weight: 600;
			text-transform: capitalize;
		}
	}
</style>
