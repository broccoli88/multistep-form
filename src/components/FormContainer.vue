<template>
	<div class="container">
		<h1 class="heading">Form</h1>
		<slot name="form"></slot>
	</div>
</template>

<style lang="scss" scoped>
	.container {
		width: 1000px;
		margin: 0 auto;
		padding: 2rem;
		background-color: lighten($bg, 2%);

		border-radius: 20px;
		box-shadow: 2px 4px 10px hsl(0, 0%, 0%, 0.4);

		display: grid;
		grid-template-columns: 1fr 30%;
		grid-template-areas:
			"heading heading "
			"form progress";

		.heading {
			grid-area: heading;
		}
	}
</style>
