<script>
	import { inview } from 'svelte-inview';
	let isInView = false;
	const options = {
		// You can configure rootMargin and other options here.
	};
</script>

<section class="rules-page">
	<div class="flare-con">
		<img class="flare f1" src="flare1-rules-mb.png" alt="flare2" />
		<img class="flare f2" src="flare2-rules-mb.png" alt="flare2" />
	</div>

	<img class="star s1" src="star1-rules-mb.png" alt="star" />
	<img class="star s2" src="star2-rules-mb.png" alt="star" />
	<img class="star s3" src="star3-rules-mb.png" alt="star" />

	<div
		use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
		class="svg {isInView ? 'show' : 'hidden'}"
	>
		<svg
			xmlns="http://www.w3.org/2000/svg"
			width="134"
			height="134"
			viewBox="0 0 134 134"
			fill="none"
		>
			<circle cx="67" cy="67" r="67" fill="url(#paint0_linear_70_6)" />
			<defs>
				<linearGradient
					id="paint0_linear_70_6"
					x1="134"
					y1="67"
					x2="3.69183"
					y2="67"
					gradientUnits="userSpaceOnUse"
				>
					<stop stop-color="#8F01FE" />
					<stop offset="1" stop-color="#FF2674" />
				</linearGradient>
			</defs>
		</svg>
	</div>

	<div
		use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
		class="woman-con {isInView ? 'show' : 'hidden'}"
	>
		<img class="woman" src="woman-rules.png" alt="woman" />
	</div>
	<div
		class="res-con {isInView ? 'show-slide' : 'hidden-slide'}"
		use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
	>
		<h2>
			Rules and<br />
			<span>Guidelines</span>
		</h2>
		<p>
			Our tech hackathon is a melting pot of visionaries, and its purpose is as clear as day: to
			shape the future. Whether you're a coding genius, a design maverick, or a concept wizard,
			you'll have the chance to transform your ideas into reality. Solving real-world problems,
			pushing the boundaries of technology, and creating solutions that can change the world, that's
			what we're all about!
		</p>
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
	.svg {
		display: none;
	}
	.rules-page {
		border-top: 1px solid rgba(255, 255, 255, 0.18);
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.woman {
		width: 294px;
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
		top: 185px;
		left: 11%;
		animation-delay: 0.3s;
	}

	.star.s2 {
		top: 442px;
		right: 42px;
		animation-delay: 0.5s;
	}

	.star.s3 {
		width: 10px;
		height: 12px;
		bottom: 19px;
		left: 108px;
		animation-delay: 0.9s;
	}

	.flare {
		z-index: -1;
		position: absolute;
	}

	.f1 {
		width: 404px;
		height: 435px;
		right: 20px;
		top: -106px;
	}

	.f2 {
		width: 252px;
		height: 446px;
		top: 192px;
		right: 0px;
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
		margin-top: 0;
		margin-bottom: 0;
		color: #fff;
		text-align: center;
		font-family: 'ClashDisplay-Bold';
		font-size: 20px;
		font-style: normal;
		font-weight: 700;
		line-height: 133%; /* 26.6px */
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
		margin-top: 9px;
		margin-left: 45px;
		margin-right: 45px;
		margin-bottom: 46px;
		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 13px;
		font-style: normal;
		font-weight: 400;
		line-height: 27.5px; /* 211.538% */
	}

	@media (min-width: 880px) {
		.svg {
			display: block;
			position: absolute;
			top: 170px;
			right: 21%;
			z-index: -1;
		}

		.star.s1 {
			width: 26px;
			height: 32px;
			top: 116px;
			left: 29%;
			animation-delay: 0.3s;
		}

		.star.s2 {
			display: none;
		}

		.star.s3 {
			width: 26px;
			height: 32px;
			bottom: 180px;
			left: 49%;
			animation-delay: 0.9s;
		}

		.f1 {
			width: 1037px;
			height: 948px;
			right: 475px;
			top: -206px;
		}

		.f2 {
			width: 404px;
			height: 959px;
			top: 40px;
			right: 0px;
		}

		.rules-page {
			flex-direction: row-reverse;
			justify-content: center;
			align-items: center;
			gap: 48px;
			padding: 78px 148px;
		}

		.res-con > * {
			max-width: 535px;
			text-align: left;
		}

		.woman-con {
			width: 664px;
		}

		p {
			margin: 0;
		}

		.woman {
			width: 100%;
			height: 100%;
			object-fit: cover;
		}

		h2 {
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
			line-height: 27.5px; /* 196.429% */
		}
	}

	@media (min-width: 1200px) {
	}
</style>
