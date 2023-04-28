<template>
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
</template>

<style lang="scss" scoped>
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
					box-shadow: $base-box-shadow;
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
					box-shadow: $base-box-shadow;
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
</style>
