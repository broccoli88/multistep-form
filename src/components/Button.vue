<template>
	<button class="btn">
		<slot name="action"></slot>
	</button>
</template>

<style lang="scss" scoped>
	.btn {
		display: block;
		padding: 0.7rem 5rem;
		margin: 2rem auto;
		border: $base-border-transparent;
		border-radius: 20px;

		font-size: 2.4rem;
		font-family: $font-changa;
		font-weight: 600;
		// color: $text;
		text-transform: uppercase;
		color: $text-transparent;

		background-color: transparent;
		cursor: pointer;

		transition: all 0.3s ease;

		&:hover,
		&:focus {
			outline: none;
			background-color: $accent;
			border: $base-border;
			box-shadow: $base-box-shadow;
			color: $text;
		}
	}
</style>
