<script>
	import { inview } from 'svelte-inview';
	let isInView = false;
	const options = {
		// You can configure rootMargin and other options here.
	};
</script>

<section class="intro-page" id="intro" >
	<img class="star s1" src="star1-intro-mb.png" alt="star" />
	<img class="star s2" src="star2-intro-mb.png" alt="star" />

	<img
		use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
		class="idea {isInView ? 'show' : 'hidden'}"
		src="idea-intro-responsive.png"
		alt="big-idea"
	/>
	<img class="arrow" src="arrow.png" alt="arrow" />

	<div
		class="res-con {isInView ? 'show-slide' : 'hidden-slide'}"
		use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
	>
		<h2>
			Introduction to getlinked<br />
			<span>tech Hackathon 1.0</span>
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
		transform: translateX(100%);
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

	.arrow {
		position: absolute;
		top: 310px;
		width: 19.456px;
		height: 22.818px;
	}

	.intro-page {
		border-top: 1px solid rgba(255, 255, 255, 0.18);
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.idea {
		height: 257px;
		margin-top: 29px;
		margin-bottom: 58px;
	}

	.star {
		position: absolute;
		display: block; /* Initially visible */
		opacity: 0; /* Initially fully transparent */
		animation: fadeInOut 2s ease-in-out infinite; /* Apply the animation infinitely */
	}

	.star.s1 {
		width: 11px;
		height: 13px;
		top: 110px;
		left: 18%;
		animation-delay: 0.3s;
	}

	.star.s2 {
		width: 12px;
		height: 14px;
		top: 386px;
		right: 13%;
		animation-delay: 0.5s;
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
		margin-top: 22.15px;
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
		margin-left: 40px;
		margin-right: 40px;
		margin-bottom: 0;
		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 13px;
		font-style: normal;
		font-weight: 400;
		line-height: 27.5px;
		margin-bottom: 75px;
	}
	@media (min-width: 880px) {
		.star.s1 {
			width: 21px;
			height: 25px;
			top: 223px;
			left: 12%;
			animation-delay: 0.3s;
		}

		.star.s2 {
			width: 30px;
			height: 36px;
			top: 216px;
			right: 11%;
			animation-delay: 0.5s;
		}

		.intro-page {
			justify-content: center;
			align-items: center;
			flex-direction: row;
			gap: 109px;
			padding: 78px 148px;
		}

		.idea {
			width: 490px;
			margin: 0;
			height: 477px;
		}

		.arrow {
			top: 80%;
			right: 50%;
			width: 49.43px;
			height: 57.974px;
		}

		.res-con > * {
			max-width: 535px;
			text-align: left;
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
	section {
		min-height: 633px;
	}

	@media (min-width: 1200px) {
	}
</style>
