<template>
	<div class="landing">
		<section class="top shadow-lg">
			<div class="background">
				<p class="brand">
					<img
						src="@/assets/img/duurzaamheid/denkt_duurzaam.png"
						alt="HMC mbo vakschool"
					/>
				</p>
			</div>
			<div class="content">
				<h3 class="subtitle fw-bolder mb-1">
					Duurzaam hergebruik van materialen uit de branche
				</h3>
				<router-link
					tag="button"
					class="btn btn-outline-default btn-lg mt-2"
					to="/libary"
					>Bekijk materialen</router-link
				>
			</div>
		</section>
		<section class="bottom">
			<small id="disclaimer">
				<span class="fw-bold">Disclaimer:</span> Dit is een tijdelijke website. Een
				nieuwe website is in ontwikkeling. <br />Deze tijdelijk website is onderdeel
				van het
				<a href="https://hmcollege.nl">Hout- en Meubileringscollege.</a>
			</small>
			<h5>OPENINGSTIJDEN CIRCUSTEK</h5>

			<h6>CIRCUSTEK</h6>
			<p>
				Ophalen gereserveerd materiaal:
				<br />Maandag 10:30 tot 14:30 uur <br />Dinsdag 13:30 tot 16:00 uur
				<br />Donderdag 8:30 tot 14:30 uur <br />Vrijdag 10:30 tot 14:30 uur
				<br />
			</p>
			<p class="mb-5">
				Meer info:
				<a href="mailto:j.vanveen@hmcollege.nl">Jacinta van Veen</a>,
				<a href="mailto:s.vandervoort@hmcollege.nl">Sjors van der Voort</a>
			</p>
		</section>
	</div>
</template>

<script>
export default {
	name: "Landing",
};
</script>

<style lang="scss" scoped>
.landing {
	z-index: 1000;
	display: flex;
	flex-direction: column;

	section {
		padding: 0 50px;
	}

	#disclaimer {
		background: #fffef9;
		padding: 0.5rem 1rem;
		position: fixed;
		left: 0;
		bottom: 0;
		text-align: left;
		z-index: 9999;
		font-size: 0.8rem;

		@media (max-width: 600px) {
			font-size: 0.6rem;
		}

		a {
			text-decoration: none;
			color: #ba0c2f;
		}
	}

	.top {
		position: relative;
		min-height: 40vh;
		max-height: 40vh;
		background: lightgrey;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		text-align: center;

		.background {
			position: absolute;
			opacity: 0.5;
			z-index: 1;
			width: 100%;
			height: 100%;
			background: url("../assets/img/background.jpg");
			background-repeat: no-repeat;
			background-size: cover;

			.brand {
				margin-bottom: 0;
				height: 55%;
				margin-top: 2vh;
				opacity: 0.9;

				img {
					height: 100%;
				}
			}
		}
		.content {
			z-index: 2;
			margin-top: 18vh;

			.title {
				font-weight: 400;
				font-size: calc(2rem + 1.5vmin);
				text-shadow: -2px 2px 0px rgba(0, 0, 0, 0.3),
					-2px 4px 2px rgba(0, 0, 0, 0.1);
			}

			.subtitle {
				font-size: calc(0.8rem + 1.5vmin);
			}

			.separator {
				position: relative;
				width: 100%;
				margin: 20px 0;
				height: 1px;
				text-align: center;

				i {
					position: absolute;
					font-size: 2vmin;
					transform: translate(-50%, -50%);
				}

				.line_left:before {
					content: "";
					position: absolute;
					top: 0;
					left: 5%;
					right: 54%;
					width: 41%;
					height: 1px;
					background-image: linear-gradient(to left, rgb(48, 49, 51), transparent);
				}

				.line_right:before {
					content: "";
					position: absolute;
					top: 0;
					left: 54%;
					right: 5%;
					width: 41%;
					height: 1px;
					background-image: linear-gradient(to right, rgb(48, 49, 51), transparent);
				}
			}
		}
	}

	.bottom {
		font-size: 1.1rem;
		padding-top: 40px;
		background-color: #fffef9;
		text-align: center;

		h4,
		h5,
		h6 {
			margin-top: 2rem;
			font-weight: 700;
		}
	}
}
</style>
