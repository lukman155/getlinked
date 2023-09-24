<script>
	import { inview } from 'svelte-inview';
	let isInView = false;
	const options = {
		// You can configure rootMargin and other options here.
	};
</script>

<section class="privacy-page">
	<img class="star s1" src="star1-privacy-mb.png" alt="star" />
	<img class="star s2" src="star2-privacy-mb.png" alt="star" />
	<img class="star s3" src="star3-privacy-mb.png" alt="star" />
	<img class="star s4" src="star4-privacy-mb.png" alt="star" />
	<img class="star s5" src="star5-privacy-mb.png" alt="star" />
	<img class="star s6" src="star6-privacy-mb.png" alt="star" />
	<img class="star s7" src="star7-privacy-mb.png" alt="star" />

	<img class="flare f1" src="flare1-rules-mb.png" alt="flare2" />

	<div class="res-con {isInView ? 'show-slide' : 'hidden-slide'}"
	use:inview={options}
	on:inview_change={(event) => (isInView = event.detail.inView)}
>
		<h2>
			Privacy Policy and<br />
			<span>Terms</span>
		</h2>
		<p class="update">Last updated on September 12, 2023</p>
		<p class="intro">
			Below are our privacy & policy, which outline a lot of goodies. it’s our aim to always take of
			our participant
		</p>
		<div class="privacy">
			<p>
				At getlinked tech Hackathon 1.0, we value your privacy and are committed to protecting your
				personal information. This Privacy Policy outlines how we collect, use, disclose, and
				safeguard your data when you participate in our tech hackathon event. By participating in
				our event, you consent to the practices described in this policy.
			</p>

			<h2>Licensing Policy</h2>
			<h3>Here are terms of our Standard License:</h3>
			<ul>
				<li>
					The Standard License grants you a non-exclusive right to navigate and register for our
					event
				</li>

				<li>
					You are licensed to use the item available at any free source sites, for your project
					developement
				</li>
			</ul>
			<div class="read-wrapper">
				<a class="read-link" href="/">Read More</a>
			</div>
		</div>
	</div>
	<div 
	use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
		class="image-con {isInView ? 'show' : 'hidden'}">
		<svg
			class="padlock-svg"
			xmlns="http://www.w3.org/2000/svg"
			width="249"
			height="311"
			viewBox="0 0 249 311"
			fill="none"
		>
			<path
				d="M249 141.364C249 219.82 195.88 293.188 124.5 311C53.12 293.188 0 219.82 0 141.364V56.5455L124.5 0L249 56.5455V141.364ZM124.5 282.727C176.375 268.591 221.333 205.543 221.333 144.474V74.9227L124.5 30.8173L27.6667 74.9227V144.474C27.6667 205.543 72.625 268.591 124.5 282.727ZM163.233 141.364V120.159C163.233 100.368 143.867 84.8182 124.5 84.8182C105.133 84.8182 85.7667 100.368 85.7667 120.159V141.364C77.4667 141.364 69.1667 149.845 69.1667 158.327V207.805C69.1667 217.7 77.4667 226.182 85.7667 226.182H161.85C171.533 226.182 179.833 217.7 179.833 209.218V159.741C179.833 149.845 171.533 141.364 163.233 141.364ZM145.25 141.364H103.75V120.159C103.75 108.85 113.433 101.782 124.5 101.782C135.567 101.782 145.25 108.85 145.25 120.159V141.364Z"
				fill="url(#paint0_linear_114_900)"
				fill-opacity="0.14"
			/>
			<defs>
				<linearGradient
					id="paint0_linear_114_900"
					x1="124.5"
					y1="0"
					x2="124.5"
					y2="311"
					gradientUnits="userSpaceOnUse"
				>
					<stop stop-color="#903AFF" />
					<stop offset="1" stop-color="#FF26B9" />
				</linearGradient>
			</defs>
		</svg>
		<div class="manlock-con">
			<img src="manlock-privacy-responsive.png" alt="manlock-icon" class="manlock-img" />
		</div>
	</div>
</section>

<style>

.hidden {
		opacity: 0;
		transition: opacity 0.3s ease-in-out; /* Add transition with a 0.3s duration and ease-in-out timing function */
	}

	.show {
		opacity: 1;
		transition: opacity 0.3s ease-in-out; /* Add the same transition for consistency */
		transition-delay: 0.3s; /* Add the same delay for consistency */
	}

	.hidden-slide {
		transform: translateX(-100%);
		filter: blur(5px);
		opacity: 0;
		transition: all 0.3s ease-in-out; /* Add transition with a 0.3s duration and ease-in-out timing function */
	}

	.show-slide {
		transform: translateX(0);
		filter: blur(0);
		opacity: 1;
		transition: all 0.3s ease-in-out; /* Add the same transition for consistency */
		transition-delay: 0.3s; /* Add the same delay for consistency */
	}

	ul {
		list-style: none; /* Remove default list bullets */
		padding-left: 30px; /* Add some left padding to make space for the checkmark */
	}

	ul > * {
		z-index: 10;
	}

	li {
		position: relative;
	}

	ul li::before {
		content: '\2713'; /* Unicode checkmark character */
		color: white; /* Green color for the checkmark */
		margin-right: 20px;
		background-color: rgb(5, 179, 5);
		border-radius: 50%;
		padding: 0.1px 5px;
		margin: 20px;
		font-size: 12px;
		position: absolute;
		top: -15px;
		left: -55px;
		/* Add some space between the checkmark and text */
	}

	.image-con {
		position: relative;
		margin-bottom: 219px;
	}
	.manlock-con {
		position: absolute;
		width: 262px;
		height: 351px;
		bottom: -66px;
		right: 5px;
	}

	.manlock-img {
		width: 100%;
		height: 100%;
		object-fit: contain;
	}

	.privacy-page {
		border-top: 1px solid rgba(255, 255, 255, 0.18);
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.update {
		color: rgba(255, 255, 255, 0.75);
		margin-bottom: 28px;
	}

	.intro {
		margin: 0 51px 30px 51px;
		line-height: 188.4%;
	}

	.privacy {
		margin: 0 46px 48px 46px;
		padding: 40px 12px;
		border-radius: 5px;
		border: 1px solid #d434fe;
		background: rgba(217, 217, 217, 0.03);
	}

	.privacy > p {
		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: 216.4%;
	}

	.privacy > * {
		margin: 0;
	}

	.privacy > h2 {
		margin-top: 21px;
		text-align: left;
		color: #d434fe;
		font-family: Montserrat;
		font-size: 13px;
		font-style: normal;
		font-weight: 700;
	}

	.privacy > h3 {
		margin-top: 5px;
		text-align: left;
		color: #fff;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 700;
		margin-bottom: 21px;
	}

	li {
		color: #fff;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: 175.9%;
		margin-bottom: 24px;
	}

	.star {
		position: absolute;
		display: block; /* Initially visible */
		opacity: 0; /* Initially fully transparent */
		animation: fadeInOut 2s ease-in-out infinite; /* Apply the animation infinitely */
	}

	.star.s1 {
		top: 43px;
		right: 96px;
		animation-delay: 0.6s;
	}

	.star.s2 {
		top: 232px;
		right: 67px;
		animation-delay: 1.2s;
	}

	.star.s3 {
		bottom: 743px;
		left: 22px;
		animation-delay: 1s;
	}

	.star.s4 {
		bottom: 438px;
		left: 39px;
		animation-delay: 0s;
	}

	.star.s5 {
		bottom: 430px;
		right: 121px;
		animation-delay: 0.6s;
	}

	.star.s6 {
		bottom: 147px;
		left: 88px;
		animation-delay: 1.5s;
	}

	.star.s7 {
		bottom: 139px;
		right: 76px;
		animation-delay: 0s;
	}

	.flare {
		z-index: -1;
		position: absolute;
		overflow: hidden;
	}

	.f1 {
		width: 285px;
		height: 366px;
		left: -80px;
		bottom: 595px;
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

	h2 {
		margin-top: 71px;
		margin-bottom: 0;
		color: #fff;
		text-align: center;
		font-family: 'ClashDisplay-Bold';
		font-size: 20px;
		font-style: normal;
		font-weight: 700;
		line-height: 133%;
	}

	h2 > span {
		color: #d434fe;
		font-family: 'ClashDisplay-Bold';

		font-size: 20px;
		font-style: normal;
		font-weight: 700;
		line-height: 133%;
	}

	p {
		margin-top: 0;
		margin-left: 40px;
		margin-right: 40px;
		margin-bottom: 0;
		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: 27.5px; /* 211.538% */
	}

	.read-wrapper {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
	}

	.read-link {
		padding: 10px 14px;
		text-decoration: none;
		color: #fff;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: normal;
		border-radius: 4px;
		background: linear-gradient(270deg, #903aff 0%, #d434fe 56.42%, #ff26b9 99.99%, #fe34b9 100%);
		text-align: center;
		margin-bottom: 20px;
	}

	.res-con {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	@media (min-width: 880px) {
		.res-con > * {
			align-self: flex-start;
		}

		.manlock-con {
			width: 530px;
			height: 648px;
			right: 30px;
			top: 220px;
		}

		.intro {
			margin: 0;
			margin-bottom: 70px;
		}
		.privacy {
			margin: 0;
			padding: 60px 72px;
		}
		.privacy > *,
		.privacy > p {
			text-align: left;
		}

		.padlock-svg {
			width: 530px;
			height: 648px;
		}

		.read-link {
			font-size: 16px;
			padding: 25px 66px;
			margin-top: 55px;
			align-self: flex-start;
		}

		.star.s1 {
			width: 26px;
			height: 32px;
			top: 159px;
			left: 514px;
			animation-delay: 0.6s;
		}

		.star.s2 {
			width: 23px;
			height: 28px;
			top: 274px;
			right: 756px;
			animation-delay: 1.2s;
		}

		.star.s3 {
			width: 15px;
			height: 18px;
			top: 727px;
			right: 546px;
			left: auto;
			animation-delay: 0s;
		}

		.star.s4 {
			width: 15px;
			height: 18px;
			top: 760px;
			left: 80px;
			animation-delay: 1s;
		}

		.star.s5 {
			width: 15px;
			height: 18px;
			top: 270px;
			right: 292px;
			animation-delay: 0.6s;
		}

		.star.s6 {
			width: 15px;
			height: 18px;
			bottom: 301px;
			right: 596px;
			left: auto;
			animation-delay: 1.5s;
		}

		.star.s7 {
			width: 26px;
			height: 32px;
			bottom: 280px;
			right: 133px;
			animation-delay: 0s;
		}

		.f1 {
			z-index: 1;
			width: 1037px;
			height: 948px;
			left: -15%;
			bottom: -300px;
		}

		.privacy-page {
			flex-direction: row;
			justify-content: center;
			align-items: center;
			gap: 48px;
			padding: 78px 148px;
			position: relative;
		}

		.res-con {
			max-width: 569;
		}

		.res-con > * {
			max-width: 564px;
			text-align: left;
		}

		h2 {
			align-self: flex-start;
			color: #fff;
			font-family: 'ClashDisplay-Bold';
			font-size: 32px;
			font-style: normal;
			font-weight: 700;
			line-height: 120%;
			margin-bottom: 16px; /* 0px */
		}

		h2 > span {
			color: #d434fe;
			font-family: 'ClashDisplay-Bold';
			font-size: 32px;
			font-style: normal;
			font-weight: 700;
		}

		p {
			margin: 0;
			color: #fff;
			font-family: Montserrat;
			font-size: 14px;
			font-style: normal;
			font-weight: 400;
			line-height: 27.5px;
			margin-bottom: 22px;
		}
	}

	@media (min-width: 1200px) {
	}
</style>
