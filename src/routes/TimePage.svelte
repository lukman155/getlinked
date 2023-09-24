<script>
	import { inview } from 'svelte-inview';
	let isInView = false;
	const options = {
		// You can configure rootMargin and other options here.
	};
</script>

<section class="time-page">
	<img class="star s1" src="star1-time-mb.png" alt="star" />
	<img class="star s2" src="star2-time-mb.png" alt="star" />
	<img class="star s3" src="star3-time-mb.png" alt="star" />

	<h2>Timeline</h2>
	<p class="intro">Here is the breakdown of the time we anticipate using for the upcoming event.</p>

	<div
	use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
		class="timeline {isInView ? 'show' : 'hidden'}">
		<div
		 class="wrapper">
			<div class="text">
				<h3>Hackathon Announcement</h3>
				<p>
					The getlinked tech hackathon 1.0 is formally announced to the general public and teams
					begin to get ready to register
				</p>
			</div>
			<div class="v-line" style="height: 137px;" />
			<div class="flex">
				<p class="no">1</p>
				<p class="date">November 18, 2023</p>
			</div>
		</div>

		<div class="wrapper">
			<div class="text">
				<h3>Teams Registration begins</h3>
				<p>
					Interested teams can now show their interest in the getlinked tech hackathon 1.0 2023 by
					proceeding to register
				</p>
			</div>
			<div class="v-line" style="height: 86px;" />
			<div class="flex">
				<p class="no">2</p>
				<p class="date">November 18, 2023</p>
			</div>
		</div>

		<div class="wrapper">
			<div class="text">
				<h3>Teams Registration ends</h3>
				<p>Interested Participants are no longer Allowed to register</p>
			</div>
			<div class="v-line" style="height: 86px;" />
			<div class="flex">
				<p class="no">3</p>
				<p class="date">November 18, 2023</p>
			</div>
		</div>

		<div class="wrapper">
			<div class="text">
				<h3>Announcement of the accepted teams and ideas</h3>
				<p>
					All teams whom idea has been accepted into getlinked tech hackathon 1.0 2023 are formally
					announced
				</p>
			</div>
			<div class="v-line" style="height: 86px;" />
			<div class="flex">
				<p class="no">4</p>
				<p class="date">November 18, 2023</p>
			</div>
		</div>

		<div class="wrapper">
			<div class="text">
				<h3>Getlinked Hackathon 1.0 Offically Begins</h3>
				<p>Accepted teams can now proceed to build their ground breaking skill driven solutions</p>
			</div>
			<div class="v-line" style="height: 86px;" />
			<div class="flex">
				<p class="no">5</p>
				<p class="date">November 18, 2023</p>
			</div>
		</div>

		<div class="wrapper">
			<div class="text">
				<h3>Demo Day</h3>
				<p>
					Teams get the opportunity to pitch their projects to judges. The winner of the hackathon
					will also be announced on this day
				</p>
			</div>
			<div class="v-line" style="height: 86px;" />
			<div class="flex">
				<p class="no">6</p>
				<p class="date">November 18, 2023</p>
			</div>
		</div>
	</div>
</section>

<style>
	.hidden {
		opacity: 0;
		transition: opacity 0.5s ease-in-out; /* Add transition with a 0.3s duration and ease-in-out timing function */
	}

	.show {
		opacity: 1;
		transition: opacity 0.5s ease-in-out; /* Add the same transition for consistency */
		transition-delay: 0.5s; /* Add the same delay for consistency */
	}
	.v-line {
		display: none;
	}
	.intro {
		margin-bottom: 54px;
	}

	.flex {
		position: relative;
		display: flex;
		width: 100%;
		align-items: center;
	}

	.timeline {
		margin: auto 54px;
		margin-bottom: 45px;
	}

	.text {
		margin-bottom: 15px;
		padding-left: 20px;
		border-left: 2px solid #d434fe;
		min-height: 90px;
	}

	.no {
		position: absolute;
		margin: 0;
		background: linear-gradient(270deg, #903aff 0%, #d434fe 100%);
		border-radius: 50%;
		padding: 2px 12px;
		left: -12px;
	}

	.date {
		margin-left: 25px;
	}

	.wrapper {
		margin-bottom: 40px;
	}

	.text > h3 {
		margin-bottom: 5px;
	}

	.text > h3,
	.date {
		color: #d434fe;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 700;
		line-height: normal;
	}

	.text > p {
		color: #fff;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: 159.9%;
		text-align: left;
		margin: 0;
	}

	.time-page {
		border-top: 1px solid rgba(255, 255, 255, 0.18);
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.star {
		position: absolute;
		display: block; /* Initially visible */
		opacity: 0; /* Initially fully transparent */
		animation: fadeInOut 2s ease-in-out infinite; /* Apply the animation infinitely */
	}

	.star.s1 {
		top: 208px;
		left: 82px;
		animation-delay: 0.6s;
	}

	.star.s2 {
		top: 688px;
		right: 95px;
		animation-delay: 1.2s;
	}

	.star.s3 {
		bottom: 37px;
		left: 22px;
		animation-delay: 0s;
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
		margin-top: 80px;
		margin-bottom: 21px;
		color: #fff;
		text-align: center;
		font-family: 'ClashDisplay-Bold';
		font-size: 20px;
		font-style: normal;
		font-weight: 700;
		line-height: 133%; /* 26.6px */
	}

	p {
		margin-top: 0;
		margin-left: 40px;
		margin-right: 40px;
		margin-bottom: 0;
		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 13px;
		font-style: normal;
		font-weight: 400;
		line-height: 27.5px; /* 211.538% */
	}

	@media (min-width: 880px) {
		.timeline {
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
			margin-bottom: 109px;
		}
		.timeline > div {
			margin-bottom: -24px;
		}

		h2 {
			font-size: 32px;
		}

		.intro {
			font-size: 14px;
			width: 346px;
		}

		.wrapper {
			display: flex;
			gap: 111px;
			align-items: baseline;
			justify-content: center;
			margin: 0;
			width: 100%;
			position: relative;
		}

		.flex {
			top: 30px;
		}

		.no {
			color: #fff;
			font-family: Montserrat;
			font-size: 24px;
			left: -130px;
		}

		.v-line {
			display: block;
			width: 0;
			height: 100%;
			border: 2px solid #d434fe;
		}

		.text {
			text-align: right;
			margin: 0;
			padding: 0;
			border: 0;
			width: 100%;
		}

		.text > p {
			text-align: right;
		}

		.text > h3 {
			font-size: 24px;
			margin: 0;
		}

		.date {
			font-size: 24px;
			position: relative;
			margin: 0;
		}

		.star.s1 {
			width: 30px;
			height: 36px;
			top: 266px;
			left: 338px;
			animation-delay: 0.6s;
		}

		.star.s2 {
			width: 26px;
			height: 32px;
			top: 620px;
			right: 266px;
			animation-delay: 1.2s;
		}

		.star.s3 {
			width: 26px;
			height: 32px;
			bottom: 123px;
			left: 177px;
			animation-delay: 0s;
		}

		.timeline .wrapper:nth-child(even) {
			flex-direction: row-reverse;
		}
		.timeline .wrapper:nth-child(even) > .text {
			text-align: left;
		}

		.timeline .wrapper:nth-child(even) > .text > p {
			text-align: left;
		}

		.timeline .wrapper:nth-child(even) > .flex {
			justify-content: flex-end;
		}

		.timeline .wrapper:nth-child(even) > .flex > .no {
			left: 582px;
		}
	}
</style>
