<script>
	import { onMount } from 'svelte';

	let text = 'Igniting a Revolution in HR Innovation';
	let displayText = '';
	let speed = 200;

	function typeWriter() {
		if (text.length > 0) {
			displayText += text.charAt(0);
			text = text.substring(1);
			setTimeout(typeWriter, speed);
		} else {
			// Animation complete, reset the text and clear the displayText
			text = 'Igniting a Revolution in HR Innovation';
			displayText = '';
			setTimeout(typeWriter, speed);
		}
	}

	onMount(() => {
		typeWriter();
	});
</script>

<section class="hero-page">
	<img class="star s1" src="star1-hero-responsive.png" alt="star" />
	<img class="star s2" src="star2-hero-responsive.png" alt="star" />
	<img class="star s3" src="star3-hero-responsive.png" alt="star" />

	<img class="flare f1" src="flare1-hero-responsive.png" alt="star" />
	<img class="flare f2" src="flare2-hero-responsive.png" alt="star" />

	<img src="man-hero-responsive.png" alt="man" class="man" />
	<img src="globe-hero-responsive.png" alt="globe" class="globe" />

	<div class="headline-wrapper">
		<h2 class="headline" id="type">{displayText}</h2>
		<svg
			class="mobile"
			xmlns="http://www.w3.org/2000/svg"
			width="117"
			height="11"
			viewBox="0 0 117 11"
			fill="none"
		>
			<path d="M1 9C20.2424 3.71764 70.7273 -3.67768 116 9" stroke="#FF26B9" stroke-width="3" />
		</svg>
		<svg
			class="desktop"
			xmlns="http://www.w3.org/2000/svg"
			width="255"
			height="17"
			viewBox="0 0 255 17"
			fill="none"
		>
			<path
				d="M1 14.043C43.3333 5.7097 154.4 -5.95697 254 14.043"
				stroke="#FF26B9"
				stroke-width="5"
			/>
		</svg>
	</div>
	<div class="title">
		<h1>
			<img class="bulb" src="creative.png" alt="creative-emoji" />
			getlinked Tech<br />
			Hackathon <span style="color:#D434FE;">1.0</span>
			<span>
				<img class="chain" src="chain.png" alt="star" />
				<img class="bang" src="bang1.png" alt="fire" />
			</span>
		</h1>
	</div>

	<p class="intro">
		Participate in getlinked tech Hackathon 2023 stand a chance to win a Big prize
	</p>

	<a href="/register" class="register-button">Register</a>
	<p class="countdown">00<span>H</span> 00<span>M</span> 00<span>S</span></p>
</section>

<style>
	.desktop {
		display: none;
	}
	.bulb {
		position: absolute;
		top: -14px;
		left: 232px;
		width: 18px;
		height: 26px;
	}

	.flare {
		position: absolute;
		overflow: hidden;
		z-index: -1;
	}

	.f1 {
		width: 390px;
		height: 442px;
		left: 0;
		top: -76px;
	}

	.f2 {
		display: none;
	}

	.bang,
	.chain {
		width: 32px;
	}

	.globe {
		z-index: 2;
		animation: pulseAndBrighten 3s infinite ease-in-out;
	}

	@keyframes pulseAndBrighten {
		0% {
			opacity: 0.6;
			transform: scale(1);
		}
		50% {
			opacity: 1.5; /* Increase opacity to brighten */
			transform: scale(1.04); /* Scale up to create pulsing effect */
		}

		100% {
			opacity: 0.6;
			transform: scale(1);
		}
	}

	.countdown {
		margin-top: 14.16px;
		color: #fff;
		font-family: Unica One;
		font-size: 48px;
		font-style: normal;
		font-weight: 400;
		line-height: 133%;
		margin-bottom: 378px;
	}

	.countdown > span {
		color: #fff;
		font-family: Montserrat;
		font-size: 14px;
		font-style: normal;
		font-weight: 400;
		line-height: 133%; /* 18.62px */
	}

	.man,
	.globe {
		position: absolute;
		right: 0%;
		bottom: 0;
		z-index: 0;
		height: 362.395px;
	}

	.man {
		filter: grayscale(100%) sepia(500%) hue-rotate(240deg);
	}

	.globe {
		right: 10%;
	}

	.register-button {
		margin-top: 24px;
		color: white;
		padding: 15px 46px;
		text-decoration: none;
		border-radius: 4px;
		background: linear-gradient(270deg, #903aff 0%, #d434fe 56.42%, #ff26b9 99.99%, #fe34b9 100%);
	}
	p {
		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 13px;
		font-style: normal;
		font-weight: 400;
		line-height: 166%;
		max-width: 264px;
		margin: 0;
	}

	/* Define animation keyframes */
	@keyframes fadeInOut {
		0% {
			opacity: 0; /* Start fully transparent */
		}
		50% {
			opacity: 1; /* Middle of animation, fully visible */
		}
		100% {
			opacity: 0; /* End of animation, fully transparent */
		}
	}

	h1 {
		font-family: 'ClashDisplay-Bold';
		margin-top: 44px;
		font-size: 32px;
		font-weight: 700;
		line-height: 39px;
		letter-spacing: 0em;
		text-align: center;
		position: relative;
		margin-bottom: 9px;
	}

	.star {
		position: absolute;
		display: block; /* Initially visible */
		opacity: 0; /* Initially fully transparent */
		animation: fadeInOut 2s ease-in-out infinite; /* Apply the animation infinitely */
	}

	.star.s1 {
		width: 10px;
		height: 12px;
		top: 81px;
		left: 31%;
		animation-delay: 0.6s;
	}

	.star.s2 {
		width: 6px;
		height: 8px;
		top: 81px;
		right: 16%;
		animation-delay: 1.2s;
	}

	.star.s3 {
		width: 6px;
		height: 8px;
		top: 275px;
		right: 23%;
		animation-delay: 0s;
	}

	.hero-page {
		border-top: 1px solid rgba(255, 255, 255, 0.1);

		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.headline-wrapper {
		display: flex;
		flex-direction: column;
		align-items: flex-end;
	}

	.headline {
		margin-top: 24px;
		color: #fff;
		font-family: Montserrat;
		font-size: 16px;
		font-style: italic;
		font-weight: 700;
		line-height: normal;
		margin-bottom: 7px;
width: 324px;
height: 14px;
	}

	@media (min-width: 880px) {
		.star.s1 {
			width: 26px;
			height: 32px;
			top: 68px;
			left: 12%;
			animation-delay: 0.6s;
		}

		.star.s2 {
			width: 26px;
			height: 32px;
			top: 146px;
			right: 44%;
		}

		.star.s3 {
			width: 26px;
			height: 32px;
			top: 605px;
			right: 61%;
		}

		.f1 {
			width: 880px;
			height: 836px;
			left: 0;
			top: -141.2px;
		}

		.f2 {
			display: block;
			z-index: 0;
			right: 0;
			top: -141.2px;
		}
		.hero-page {
			align-items: flex-start;
			padding: 0 65px;
		}

		.headline-wrapper {
			align-self: flex-end;
		}

		h1 {
			font-size: 50px;
			text-align: left;
			line-height: 50px;
		}
		.countdown {
			font-size: 64px;
			font-weight: 400;
			margin: 0;
			margin-bottom: 95px;
		}

		.man,
		.globe {
			position: absolute;
			right: 0;
			bottom: 0;
			z-index: 0;
			height: 80%;
		}

		.man {
			filter: grayscale(100%) sepia(500%) hue-rotate(240deg);
		}

		.globe {
			right: 4%;
			bottom: 10%;
		}
		.bang {
			width: 58px;
			height: 58px;
		}

		.bulb {
			top: -30px;
			left: 320px;
			width: 30px;
			height: 40px;
		}

		.headline {
		width: 727px;
		height: 36px;
	}

	.mobile {
		display: none;
	}

	.desktop {
		display: block;
	}

	}


	@media (min-width: 1200px) {
		.bulb {
			top: -55px;
			left: 510px;
			width: 53px;
			height: 73px;
		}

		.f1 {
			width: 1086px;
		}
		.hero-page {
			align-items: flex-start;
			padding: 0 130px;
		}

		h2.headline {
			margin-top: 32px;
			font-size: 36px;
		}
		.headline-wrapper {
			margin-bottom: 100px;
		}

		h1 {
			font-size: 80px;
			text-align: left;
			line-height: 80px;
			margin-bottom: 8px;
		}

		.chain {
			position: relative;
			top: 10px;
			width: 75px;
		}

		.line {
			width: 253px;
			height: 11.043px;
		}

		.intro {
			color: #fff;
			font-family: Montserrat;
			font-size: 20px;
			font-style: normal;
			font-weight: 400;
			line-height: 166%;
			text-align: left;
			max-width: 522px;
			margin-bottom: 41;
			z-index: 1;
		}

		.register-button {
			color: #fff;
			font-family: Montserrat;
			font-size: 16px;
			font-style: normal;
			font-weight: 400;
			line-height: normal;
			padding-right: 52px;
			padding-left: 52px;
			margin-bottom: 77px;
		}

		.countdown {
			font-size: 64px;
			font-weight: 400;
			margin: 0;
			margin-bottom: 95px;
		}

		.man,
		.globe {
			position: absolute;
			right: 0;
			bottom: 0;
			z-index: 0;
		}

		.man {
			filter: grayscale(100%) sepia(500%) hue-rotate(240deg);
		}

		.globe {
			right: 4%;
			bottom: 10%;
		}
	}
</style>
