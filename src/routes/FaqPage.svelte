<script>

	import { inview } from 'svelte-inview';
	let isInView = false;
	const options = {
		// You can configure rootMargin and other options here.
	};


	const questions = [
		{
			question: 'Can I work on a project I started before the hackathon?',
			answer:
				'Lorem ipsum dolor sit amet consectetur adipisicing elit. Ratione quod, quibusdam, delectus natus placeat, fugiat culpa labore magnam nesciunt ipsum fuga provident sequi. Veniam provident dignissimos tempore laudantium id optio.'
		},
		{
			question: 'What happens if I need help during the hackathon?',
			answer:
				'Lorem ipsum dolor sit amet consectetur adipisicing elit. Ratione quod, quibusdam, delectus natus placeat, fugiat culpa labore magnam nesciunt ipsum fuga provident sequi. Veniam provident dignissimos tempore laudantium id optio.'
		},
		{
			question: "What happens if I don't have an idea for a project?",
			answer:
				'Lorem ipsum dolor sit amet consectetur adipisicing elit. Ratione quod, quibusdam, delectus natus placeat, fugiat culpa labore magnam nesciunt ipsum fuga provident sequi. Veniam provident dignissimos tempore laudantium id optio.'
		},
		{
			question: 'Can I join a team or do I have to come with one?',
			answer:
				'Lorem ipsum dolor sit amet consectetur adipisicing elit. Ratione quod, quibusdam, delectus natus placeat, fugiat culpa labore magnam nesciunt ipsum fuga provident sequi. Veniam provident dignissimos tempore laudantium id optio.'
		},
		{
			question: 'What happens after the hackathon ends',
			answer:
				'Lorem ipsum dolor sit amet consectetur adipisicing elit. Ratione quod, quibusdam, delectus natus placeat, fugiat culpa labore magnam nesciunt ipsum fuga provident sequi. Veniam provident dignissimos tempore laudantium id optio.'
		},
		{
			question: 'Can I work on a project I started before the hackathon?',
			answer:
				'Lorem ipsum dolor sit amet consectetur adipisicing elit. Ratione quod, quibusdam, delectus natus placeat, fugiat culpa labore magnam nesciunt ipsum fuga provident sequi. Veniam provident dignissimos tempore laudantium id optio.'
		}
	];

	let isOpen = [false, false, false, false, false, false];

	function toggleQuestion(index) {
		isOpen[index] = !isOpen[index];
	}
</script>

<section class="faq-page">
	<img class="star s1" src="star1-faq-mb.png" alt="star" />
	<img class="star s2" src="star2-faq-mb.png" alt="star" />
	<img class="star s3" src="star3-faq-mb.png" alt="star" />
	<img class="star s4" src="star4-faq-mb.png" alt="star" />
	<img class="star s5" src="star5-faq-mb.png" alt="star" />
	<div class="res-con">
		<h2 class="{isInView ? 'show-slide' : 'hidden-slide'}"
		use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}>
			Frequently Ask<br />
			<span>Question</span>
		</h2>

		<p class="intro {isInView ? 'show-slide' : 'hidden-slide'}"
		use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}>
			We got answers to the questions that you might want to ask about getlinked Hackathon 1.0
		</p>

		<!-- svelte-ignore a11y-unknown-aria-attribute -->
		<!-- svelte-ignore a11y-no-static-element-interactions -->
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<div class="accordion-container {isInView ? 'show-slide' : 'hidden-slide'}"
		use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}>
			{#each questions as question, index}
				<div class="accordion"
			 on:click={() => toggleQuestion(index)}>
					<div class="ask" aria-role="button">
						<p>{question.question}</p>
						<p class="plus">+</p>
					</div>
					<div
						class="answer"
						aria-hidden="true"
						style="display: {isOpen[index] ? 'block' : 'none'}"
					>
						<p>{question.answer}</p>
					</div>
				</div>
			{/each}
		</div>

		<div class="question-icons">
			<p class="q1">?</p>
			<p class="q2">?</p>
			<p class="q3">?</p>
		</div>
	</div>

	<img
	use:inview={options}
	on:inview_change={(event) => (isInView = event.detail.inView)}
	class="man-img {isInView ? 'show' : 'hidden'}" src="man-faq-mb.png" alt="man-think" />
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
	.question-icons > p {
		position: absolute;
		font-family: 'MADE TOMMY Outline';
		font-style: normal;
		font-weight: 500;
		line-height: 27.5px;
		margin: 0;
		animation: shakeFloat 3s ease-in-out infinite; /* Apply the animation */
	}

	.q1 {
		color: #d434fe;
		font-size: 64px;
		left: 36%;
		bottom: 0px;
	}

	.q2 {
		color: #a866fd;
		font-size: 40px;
		left: 20%;
		bottom: -20px;
	}

	.q3 {
		color: #a866fd;
		font-size: 40px;
		left: 56%;
		bottom: -20px;
	}

	/* Define the animation keyframes */
	@keyframes shakeFloat {
		0% {
			transform: translatey(0px);
		}
		50% {
			transform: translatey(-10px);
		}
		100% {
			transform: translatey(0px);
		}
	}

	.faq-page {
		border-top: 1px solid rgba(255, 255, 255, 0.18);
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.man-img {
		width: 327px;
		height: 327px;
		margin-bottom: 49px;
	}

	.star {
		position: absolute;
		display: block; /* Initially visible */
		opacity: 0; /* Initially fully transparent */
		animation: fadeInOut 2s ease-in-out infinite; /* Apply the animation infinitely */
	}

	.star.s1 {
		top: 47px;
		left: 59px;
		animation-delay: 0.4s;
	}

	.star.s2 {
		bottom: 376px;
		right: 194px;
		animation-delay: 1.4s;
	}

	.star.s3 {
		bottom: 267px;
		left: 98px;
		animation-delay: 2s;
	}

	.star.s4 {
		bottom: 206px;
		left: 50px;
		animation-delay: 0.1s;
	}

	.star.s5 {
		bottom: 44px;
		right: 92px;
		animation-delay: 1s;
	}

	.res-con {
		display: flex;
		flex-direction: column;
		align-items: center;
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
		margin-top: 60px;
		margin-bottom: 6px;
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
		font-family: Montserrat;
		font-size: 12px;
	}

	p.intro {
		margin-top: 0;
		margin-left: 48px;
		margin-right: 48px;
		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: 27.5px; /* 229.167% */
		margin-bottom: 45.69px;
	}

	.plus {
		color: #d434fe;
		font-family: Montserrat;
		font-size: 20px;
		font-style: normal;
		font-weight: 400;
		line-height: 27.5px; /* 137.5% */
	}

	.accordion-container {
		display: flex;
		flex-direction: column;
		gap: 5px;
		margin: 0 48px;
		margin-bottom: 86px;
	}

	.accordion {
		border-bottom: 1px solid #d434fe;
		margin-bottom: 20px;
		cursor: pointer;
		width: 296px;
		/* Add cursor pointer for the accordion */
	}

	/* Hide the answer by default */
	.accordion .answer {
		display: none;
	}

	/* Style the "+" sign */
	.ask > p {
		margin-bottom: 5px;
		margin-top: 0;
	}

	.answer > p {
		color: #d434fe;
	}

	.ask {
		display: flex;
		justify-content: space-between;
	}

	@media (min-width: 880px) {
		.q1 {
			color: #d434fe;
			font-size: 128px;
			left: auto;
			right: 581px;
			top: 170px;
		}

		.q2 {
			color: #a866fd;
			font-size: 96px;
			left: auto;
			right: 730px;
			top: 202px;
		}

		.q3 {
			color: #a866fd;
			font-size: 96px;
			left: auto;
			right: 454px;
			top: 202px;
			bottom: auto;
		}

		.star.s1 {
			width: 26px;
			height: 32px;
			top: 110px;
			left: 183px;
			animation-delay: 0.3s;
		}

		.star.s2 {
			width: 21px;
			height: 25px;
			top: 97px;
			left: 1020px;
		}

		.star.s3 {
			width: 21px;
			height: 25px;
			top: 253px;
			left: 819px;
			animation-delay: 0.9s;
		}
		.star.s4 {
			width: 26px;
			height: 32px;
			top: 496px;
			left: 720px;
			animation-delay: 0.9s;
		}

		.star.s5 {
			width: 26px;
			height: 32px;
			bottom: 47px;
			right: 260px;
			animation-delay: 0.9s;
		}

		.man-img {
			width: 401px;
			height: 401px;
			margin: 0;
			margin-top: 122px;
		}

		.faq-page {
			flex-direction: row;
			justify-content: center;
			align-items: center;
			gap: 48px;
			padding: 78px 148px;
			position: relative;
		}

		.accordion-container {
			gap: 10px;
			margin: 0;
			width: 427px;
		}

		.accordion {
			width: 427px;
		}

		.res-con > * {
			text-align: left;
		}

		p {
			margin: 0;
		}

		.res-con > h2 {
			align-self: flex-start;
			color: #fff;
			font-family: 'ClashDisplay-Bold';
			font-size: 32px;
			font-style: normal;
			font-weight: 700;
			line-height: 120%;
			margin: 0;
			margin-bottom: 16px;
		}

		.res-con > P {
			align-self: flex-start;

			max-width: 342px;
			font-size: 14px;
			margin: 0;
			margin-bottom: 69px;
			text-align: left;
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
		.man-img {
			width: 741px;
			height: 741px;
			margin: 0;
			margin-top: 122px;
		}
	}
</style>
