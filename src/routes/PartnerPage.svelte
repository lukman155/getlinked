<script>
	import { inview } from 'svelte-inview';
	let isInView = false;
	const options = {
		// You can configure rootMargin and other options here.
	};
</script>

<section class="partner-page">
	<img class="star s1" src="star1-partner-mb.png" alt="star" />
	<img class="star s2" src="star2-partner-mb.png" alt="star" />
	<img class="star s3" src="star3-partner-mb.png" alt="star" />

	<img class="flare f1" src="flare1-partner-mb.png" alt="flare2" />
	<img class="flare f2" src="flare2-partner-mb.png" alt="flare2" />

	<h2>Partners and Sponsors</h2>

	<p class="intro">
		Getlinked Hackathon 1.0 is honored to have the following major companies as its partners and
		sponsors
	</p>

	<div class="company-logo">
		<div class="logo l1">
			<img src="liberty-1st-mb.png" alt="liberty-logo" 
			use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
		class="{isInView ? 'show' : 'hidden'}"/>
		</div>

		<div class="logo v-line" />

		<div class="logo l2">
			<img src="liberty-2nd-mb.png" alt="liberty-logo"
			use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
		class="{isInView ? 'show' : 'hidden'}" />
		</div>

		<div class="logo v-line" />

		<div class="logo l3">
			<img src="winwise-3rd-mb.png" alt="liberty-logo" 
			use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
		class="{isInView ? 'show' : 'hidden'}"/>
		</div>

		<div class="logo h-line" />

		<div class="logo empty-line" />

		<div class="logo h-line" />

		<div class="logo empty-line" />

		<div class="logo h-line" />

		<div class="logo l4">
			<img src="whisper-4th-mb.png" alt="liberty-logo" use:inview={options}
			on:inview_change={(event) => (isInView = event.detail.inView)}
			class="{isInView ? 'show' : 'hidden'}"/>
		</div>

		<div class="logo v-line" />

		<div class="logo l5">
			<p
			use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
		class="pay {isInView ? 'show' : 'hidden'}">Pay<span>box</span></p>
		</div>

		<div class="logo v-line" />

		<div
		use:inview={options}
		on:inview_change={(event) => (isInView = event.detail.inView)}
		class="logo l6 {isInView ? 'show' : 'hidden'}">
			<p class="why ">Vuzual <span>Plus</span></p>
			<p class="why2">Design Studios</p>
		</div>
	</div>
</section>

<style>

.hidden {
	transform: scale(0);
		opacity: 0;
		transition: all 0.6s ease-in-out; /* Add transition with a 0.3s duration and ease-in-out timing function */
	}

	.show {
		opacity: 1;
		transform: scale(1);
		transition: all 0.6s ease-in-out; /* Add the same transition for consistency */
		transition-delay: 0.2s; /* Add the same delay for consistency */
	}
	.pay {
		color: #fff;
		font-family: Typo Hoop Demo;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: 27.5px;
		margin: 0;
	}

	.pay > span {
		color: #00a3ff;
	}

	.why {
		margin: 0;
		color: #fff;
		font-family: Voces;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: 27.5px; /* 229.167% */
	}

	.why > span {
		color: #f00;
		font-family: Volkhov;
	}

	.l6 {
		position: relative;
	}

	.why2 {
		position: absolute;
		color: #fff;
		font-family: Voces;
		font-size: 4px;
		font-style: normal;
		font-weight: 400;
		bottom: 5px;
		right: -1px;
		margin: 0;
	}

	.company-logo {
		display: grid;
		padding: 38.25px 45px;
		margin: 30px;
		grid-template-columns: 1fr auto 1fr auto 1fr; /* Three columns with equal width */
		grid-template-rows: 1fr auto 1fr; /* Two rows with equal height */
		/* Gap between grid items */
		margin: 0px 30px 104.41px 30px;
		border: 1px solid #d434fe;
		gap: 7px;
	}

	.logo {
		display: flex;
		align-items: center;
		justify-content: center;
		text-align: center; /* Center the content */
		width: 70px;
		height: 30px;
	}

	.logo > img {
		width: 100%;
		height: 100%;
		object-fit: contain;
	}

	.empty-line {
		height: 0;
		padding: 0;
		width: 0;
		margin: 0;
	}

	.v-line {
		width: 0;
		padding: 0;
		border-right: 1px solid #d434fe;
		border-left: 1px solid #d434fe;
	}

	.h-line {
		height: 0;
		padding: 0;
		border-top: 1px solid #d434fe;
		border-bottom: 1px solid #d434fe;
	}

	.partner-page {
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
		top: 178px;
		left: 52px;
		animation-delay: 0.6s;
	}

	.star.s2 {
		top: 232px;
		right: 170px;
		animation-delay: 1.2s;
	}

	.star.s3 {
		bottom: 108px;
		right: 71px;
		animation-delay: 0s;
	}

	.flare {
		z-index: -1;
		position: absolute;
		overflow: hidden;
	}

	.f1 {
		left: -13px;
		top: -98px;
		z-index: 2;
	}

	.f2 {
		bottom: -177px;
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
		margin-top: 41px;
		margin-bottom: 5px;
		color: #fff;
		text-align: center;
		font-family: 'ClashDisplay-Bold';
		font-size: 20px;
		font-style: normal;
		font-weight: 700;
		line-height: 133%; /* 26.6px */
	}

	.intro {
		margin: 0 52px 41px 52px;

		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: 20.5px; /* 170.833% */
	}

	@media (min-width: 880px) {
		.partner-page {
			height: 972px;
		}

		.company-logo {
			/* width: 1255px;
			height: 560px; */
			transform: scale(3);
			margin: 0;
			margin-top: 100px;
		}
		.f1 {
			width: 1037px;
			height: 948px;
			left: -259px;
			top: -114px;
		}

		.f2 {
			width: 1037px;
			height: 948px;
			bottom: -400px;
			right: -400px;
			left: auto;
		}

		.star.s1 {
			width: 26px;
			height: 32px;
			top: 270px;
			left: 330px;
			animation-delay: 0.6s;
		}

		.star.s2 {
			width: 21px;
			height: 25px;
			top: auto;
			bottom: 570px;
			right: 45%;
			animation-delay: 1.2s;
		}

		.star.s3 {
			width: 26px;
			height: 32px;
			bottom: 264px;
			left: auto;
			right: 45%;
			animation-delay: 0s;
		}

		h2 {
			color: #fff;
			font-family: 'ClashDisplay-Bold';
			font-size: 32px;
			font-style: normal;
			font-weight: 700;
			margin-top: 114px;
			margin-bottom: 24px;
		}

		.partner-page > p {
			width: 452px;
			font-size: 14px;
			font-style: normal;
			font-weight: 400;
			line-height: 27.5px;

			margin-bottom: 130px;
		}
	}

	@media (min-width: 1200px) {
	}
</style>
