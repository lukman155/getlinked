<section class="prize-page">
	<img class="star s1" src="star1-prize-mb.png" alt="star" />
	<img class="star s2" src="star2-prize-mb.png" alt="star" />
	<img class="star s3" src="star3-prize-mb.png" alt="star" />
	<img class="star s4" src="star4-prize-mb.png" alt="star" />
	<img class="star s5" src="star5-prize-mb.png" alt="star" />
	<img class="flare f1" src="flare1-prize-mb.png" alt="flare2" />
	<img class="flare f2" src="flare2-prize-mb.png" alt="flare2" />

	<img class="cup-img desk" src="cup-prize-mb.png" alt="cup" />
	<div class="res-con">
		<h2>
			Prizes and<br />
			<span>Rewards</span>
		</h2>
		<p>Highlight of the prizes or rewards for winners and for participants.</p>

		<img class="cup-img mobile" src="cup-prize-mb.png" alt="cup" />

		<div class="medal-wrapper">
			<div class="medal m1">
				<img src="medal1-prize-mb.png" alt="medal" />
				<p><span>2nd</span><br />Runner</p>
				<h3>N300,000</h3>
			</div>

			<div class="medal m2">
				<img src="medal2-prize-mb.png" alt="medal" />
				<p><span>1st</span><br />Runner</p>
				<h3>N500,000</h3>
			</div>

			<div class="medal m3">
				<img src="medal3-prize-mb.png" alt="medal" />
				<p><span>3rd</span><br />Runner</p>
				<h3>N150,000</h3>
			</div>
		</div>
	</div>
</section>

<style>
	.desk {
		display: none;
	}

	.medal-wrapper {
		display: flex;
		margin-bottom: 89.27px;
		width: 100%;
		justify-content: center;
		gap: 13px;
	}

	.medal {
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-end;
		height: 126px;
		padding: 0 18px;
		border-radius: 8px;
		border: 1px solid #d434fe;
		background: rgba(212, 52, 254, 0.12);
	}

	.medal > img {
		position: absolute;
	}

	.m1 > img {
		z-index: 1;
		top: -40px;
	}

	.m2 > img {
		z-index: 1;
		top: -70px;
	}

	.m3 > img {
		z-index: 1;
		top: -40px;
	}

	.medal > p {
		color: #fff;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 600;
		line-height: 216.4%; /* 25.968px */
		margin: 0;
	}

	.medal > h3 {
		color: #d434fe;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 700;
		line-height: 216.4%; /* 25.968px */
		margin: 0;
	}

	.m2 {
		color: #903aff;
		height: 136px;
		border-radius: 8px;
		border: 1px solid #903aff;
		background: rgba(144, 58, 255, 0.12);
	}

	.medal.m2 > h3 {
		color: #903aff;
	}

	.prize-page {
		background-color: #150e28;
		background-image: url('bg-prize-mb.png');
		background-size: cover;
		background-repeat: no-repeat;
		background-blend-mode: color-burn;
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.prize-page > * {
		z-index: 2;
	}

	.cup-img {
		margin-bottom: 121px;
	}

	.star {
		position: absolute;
		display: block; /* Initially visible */
		opacity: 0; /* Initially fully transparent */
		animation: fadeInOut 2s ease-in-out infinite; /* Apply the animation infinitely */
	}

	.star.s1 {
		top: 49px;
		left: 57px;
		animation-delay: 0.6s;
	}

	.star.s2 {
		top: 94px;
		right: 110px;
		animation-delay: 1.2s;
	}

	.star.s3 {
		bottom: 344px;
		left: 68px;
		animation-delay: 0s;
	}

	.star.s4 {
		bottom: 285px;
		right: 61px;
		animation-delay: 0.2s;
	}

	.star.s5 {
		bottom: 31px;
		right: 137px;
		animation-delay: 1.1s;
	}

	.flare {
		z-index: 1;
		position: absolute;
		overflow: hidden;
	}

	.f1 {
		width: 403px;
		height: 444px;
		left: 0px;
		top: 0px;
	}

	.f2 {
		width: 249px;
		height: 444px;
		top: 441px;
		left: 155px;
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
		margin-top: 72px;
		margin-bottom: 3px;
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
		margin-top: 0;
		margin-left: 57px;
		margin-right: 57px;
		margin-bottom: 40px;
		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 13px;
		font-style: normal;
		font-weight: 400;
		line-height: 27.5px; /* 211.538% */
	}

	.res-con {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	@media (min-width: 880px) {
		.desk {
			display: block;
		}
		.mobile {
			display: none;
		}

		.cup-img {
			width: 548px;
			margin: 0;
		}

		h2 {
			margin: 0;
		}

		.medal-wrapper {
			gap: 24px;
			margin: 0;
			margin-top: 264px;
		}

		.medal {
			width: 212px;
			height: 296px;
		}

		.medal.m2 {
			width: 212px;
			height: 315px;
		}

		.medal > p {
			font-size: 24px;
			font-style: normal;
			font-weight: 600;
		}

		.medal > p > span {
			font-size: 40px;
			font-style: normal;
			font-weight: 700;
		}

		.medal > h3 {
			font-size: 32px;
			font-weight: 700;
		}

		.m1 > img {
			width: 179px;
			height: 180px;
			z-index: 1;
			top: -100px;
		}

		.m2 > img {
			z-index: 1;
			width: 296px;
			height: 296px;
			top: -170px;
		}

		.m3 > img {
			width: 179px;
			height: 180px;
			z-index: 1;
			top: -100px;
		}

		.f1 {
			width: 1037px;
			height: 948px;
			left: 0px;
			top: 0px;
		}

		.f2 {
			width: 404px;
			height: 959px;
			top: 300px;
			right: -20px;
			left: auto;
		}

		.star.s1 {
			width: 26px;
			height: 32px;
			top: 80px;
			left: 7%;
			animation-delay: 0.3s;
		}

		.star.s2 {
			width: 26px;
			height: 32px;
			top: 500px;
			left: 33%;
		}

		.star.s3 {
			width: 26px;
			height: 32px;
			top: 820px;
			left: 52%;
			animation-delay: 0.9s;
		}

		.prize-page {
			flex-direction: row;
			justify-content: center;
			align-items: center;
			gap: 48px;
			padding: 78px 148px;
			position: relative;
		}

		.res-con > * {
			max-width: 692px;
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
			margin-bottom: 16px;
			margin-left: 180px;
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
			margin-bottom: 22px;
			margin-left: 130px;
			text-align: left;
		}

		P > span {
			font-size: 16px;
		}

		.medal-wrapper * {
			transform: scale(0.7);
		}

		.medal-wrapper {
			gap: 5px;
		}
	}

	@media (min-width: 1200px) {
		.medal-wrapper * {
			transform: scale(1);
		}

		.medal-wrapper {
			gap: 20px;
		}
	}
</style>
