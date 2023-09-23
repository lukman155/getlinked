<section class="judge-page">
	<div class="svg">
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
	<img class="star s1" src="star1-judge-mb.png" alt="star" />
	<img class="star s2" src="star2-judge-mb.png" alt="star" />
	<img class="star s3" src="star3-judge-mb.png" alt="star" />

	<img class="flare f1" src="flare-judge-mb.png" alt="flare2" />
	<img class="flare f2" src="flare-judge-mb.png" alt="flare2" />

	<img class="people-img" src="people-judge-mb.png" alt="people" />

	<div class="res-con">
		<h2>
			Judging Criteria<br />
			<span>Key attributes</span>
		</h2>
		<p>
			<span>Innovation and Creativity:</span> Evaluate the uniqueness and creativity of the solution.
			Consider whether it addresses a real-world problem in a novel way or introduces innovative features.
		</p>
		<p>
			<span>Functionality:</span> Assess how well the solution works. Does it perform its intended functions
			effectively and without major issues? Judges would consider the completeness and robustness of
			the solution.
		</p>
		<p>
			<span>Impact and Relevance:</span> Determine the potential impact of the solution in the real world.
			Does it address a significant problem, and is it relevant to the target audience? Judges would
			assess the potential social, economic, or environmental benefits.
		</p>
		<p>
			<span>Technical Complexity:</span> Evaluate the technical sophistication of the solution. Judges
			would consider the complexity of the code, the use of advanced technologies or algorithms, and
			the scalability of the solution.
		</p>
		<p>
			<span>Adherence to Hackathon Rules:</span> Judges will Ensure that the team adhered to the rules
			and guidelines of the hackathon, including deadlines, use of specific technologies or APIs, and
			any other competition-specific requirements.
		</p>

		<a class="read-link" href="/">Read More</a>
	</div>
</section>

<style>
	.svg {
		display: none;
	}

	.judge-page {
		border-top: 1px solid rgba(255, 255, 255, 0.18);
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.people-img {
		width: 332px;
		margin-top: 74px;
	}

	.star {
		position: absolute;
		display: block; /* Initially visible */
		opacity: 0; /* Initially fully transparent */
		animation: fadeInOut 2s ease-in-out infinite; /* Apply the animation infinitely */
	}

	.star.s1 {
		width: 13px;
		height: 17px;
		top: 15px;
		left: 45%;
		animation-delay: 0.6s;
	}

	.star.s2 {
		width: 12px;
		height: 14px;
		top: 221px;
		right: 46%;
		animation-delay: 1.2s;
	}

	.star.s3 {
		width: 10px;
		height: 12px;
		bottom: 70px;
		left: 90%;
		animation-delay: 0s;
	}

	.flare {
		z-index: -1;
		position: absolute;
		overflow: hidden;
	}

	.f1 {
		width: 404px;
		height: 444px;
		left: 0px;
		top: 74px;
	}

	.f2 {
		transform: rotate(180deg);
		width: 252px;
		height: 444px;
		bottom: -47px;
		right: -12%;
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
		margin-top: -7px;
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
		line-height: 27.5px; /* 211.538% */
	}

	p > span {
		color: #ff26b9;
		text-align: center;
		font-family: Montserrat;
		font-size: 13px;
		font-style: normal;
		font-weight: 700;
		line-height: 173.5%; /* 22.555px */
	}

	.read-link {
		margin-top: 25px;
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
		margin-bottom: 60px;
	}

	.res-con {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	@media (min-width: 880px) {
		.svg {
			display: block;
			position: absolute;
			top: 200px;
			left: 15.5%;
			z-index: -1;
		}

		.read-link {
			font-size: 16px;
			padding: 25px 66px;
			margin-top: 55px;
			align-self: flex-start;
		}

		.people-img {
			width: 400px;
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

		.f1 {
			width: 1037px;
			height: 948px;
			right: -10%;
			top: 216px;
		}

		.f2 {
			width: 1037px;
			height: 948px;
			top: 475px;
			right: -200px;
		}

		.people-img {
			margin: 0;
		}

		.judge-page {
			flex-direction: row;
			justify-content: center;
			align-items: center;
			gap: 48px;
			padding: 78px 148px;
			position: relative;
		}

		.res-con > * {
			max-width: 564px;
			text-align: left;
		}

		p {
			margin: 0;
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

		P > span {
			font-size: 16px;
		}
	}

	@media (min-width: 1200px) {
		.people-img {
			width: 650px;
		}
	}
</style>
