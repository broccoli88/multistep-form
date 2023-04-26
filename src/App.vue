<template>
	<div class="container">
		<h1 class="heading">Form</h1>
		<form action="" class="form">
			<fieldset class="fieldset">
				<legend class="legend">page 1</legend>
				<div class="input-container">
					<label class="label" for="">username</label>
					<input class="input" type="text" />
				</div>
				<div class="input-container">
					<label class="label" for="">username</label>
					<input class="input" type="text" />
				</div>
				<div class="input-container">
					<label class="label" for="">username</label>
					<input class="input" type="text" />
				</div>
			</fieldset>
		</form>
		<section class="progress">
			<div>
				<h2>1</h2>
			</div>
		</section>
	</div>
</template>

<style lang="scss" scoped>
	.container {
		width: 1000px;
		margin: 0 auto;
		padding: 2rem;
		background-color: $secondary-bg;

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

	.form {
		grid-area: form;
	}

	.fieldset {
		border-radius: 20px;
		border-color: $chinesViolet;
		padding: 2rem;

		.legend {
			font-size: 3rem;
			font-weight: 600;
			text-transform: capitalize;
		}
	}

	.input-container {
		margin-bottom: 3rem;

		.label {
			display: block;
			font-size: 1.7rem;
			font-weight: 600;
			text-transform: capitalize;
		}
		.input {
			display: block;
			width: 100%;
			padding: 0.5rem 1.2rem;
			border: none;
			border-radius: 10px;
			background-color: hsl(21, 69%, 68%);
			font-size: 1.6rem;
			color: $text;
		}
	}

	.progress {
		grid-area: progress;
	}
</style>
