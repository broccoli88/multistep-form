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
			<button class="btn">next</button>
		</form>
		<section class="progress-section">
			<div class="progress-container">
				<span class="progress">
					<p>1</p>
				</span>
				<span class="progress">
					<p>2</p>
				</span>
				<span class="progress">
					<p>3</p>
				</span>
				<span class="progress">
					<p>4</p>
				</span>
			</div>
		</section>
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
			padding: 0.8rem 1.2rem;
			border: none;
			border-radius: 10px;
			background-color: lighten($bg, 5%);
			font-size: 2rem;
			color: $text;
		}
	}

	.progress-section {
		grid-area: progress;
		display: grid;
		// place-content: center;
		.progress-container {
			height: 400px;
			display: flex;
			flex-direction: column;
			// justify-content: space-around;
			align-items: center;
			justify-content: center;

			.progress {
				display: block;
				width: 60px;
				height: 60px;
				border: $base-border-transparent;
				border-radius: 50%;
				color: $text-transparent;
				margin-bottom: 3rem;
				display: flex;
				justify-content: center;
				align-items: center;
				position: relative;

				&:first-child {
					color: $text;
					border: $base-border;
					background-color: $accent;
				}

				&::before {
					content: "";
					display: block;
					position: absolute;
					height: 3.3rem;
					width: 3px;
					bottom: calc((-3rem + -21px));
					left: 50%;
					z-index: 2;
					transform: translateY(-50%);
					background-color: $text-transparent;
				}

				&:first-child::before {
					background-color: $text;
				}

				&:last-child::before {
					display: none;
				}

				p {
					font-size: 2rem;
					font-weight: 600;
				}
			}
		}
	}
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

		&:hover {
			background-color: $accent;
			border-color: $base-border;
			box-shadow: $base-box-shadow;
			color: $text;
		}
	}
</style>
