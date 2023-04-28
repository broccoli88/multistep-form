<script setup>
	import { ref } from "vue";

	const props = defineProps({
		firstName: String,
		firstNameError: String,
	});

	const emit = defineEmits(["update:firstName"]);
	const updateFirstName = (e) => {
		emit("update:firstName", e.target.value);
	};

	// VUELIDATE
</script>

<template>
	<div class="input-container">
		<label class="label" for="">
			<slot name="field-name"></slot>
		</label>
		<input
			class="input"
			type="text"
			:value="firstName"
			@input="updateFirstName"
		/>
		<p class="error">
			<slot name="error"></slot>
		</p>
	</div>
</template>

<style lang="scss" scoped>
	.input-container {
		margin-bottom: 3rem;

		.label {
			display: block;
			font-size: 1.7rem;
			font-weight: 500;
			text-transform: capitalize;
		}
		.input {
			display: block;
			width: 100%;
			padding: 0.5rem 1.2rem;
			border: none;
			border-radius: 10px;
			background-color: lighten($bg, 5%);
			font-size: 2rem;
			font-family: $font-changa;
			color: $text;
			transition: box-shadow 0.3s ease;

			&:focus {
				box-shadow: $base-box-shadow;
				outline: 1px solid $accent;
			}
		}

		.error {
			color: firebrick;
		}
	}
</style>
