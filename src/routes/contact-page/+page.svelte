<script>
	import Navbar from './../Navbar.svelte';

	let teamName = '';
	let email = '';
	let topic = '';
	let message = '';

	let modalVisible = false;

	const handleSubmit = async (event) => {
  event.preventDefault();

  // Perform form validation here
  if (!teamName || !topic || !email || !message) {
    alert('Please fill in all required fields.');
    return;
  }

  const contactFormData = {
    email,
    first_name: teamName, // Assuming teamName corresponds to first_name
    message,
  };

  try {
    const response = await fetch('https://backend.getlinked.ai/hackathon/contact-form', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify(contactFormData),
    });

    if (response.status === 201) {
      // Contact form submission successful
      // You can handle success as needed, e.g., show a success message or redirect
      console.log('Contact form submission successful');
    } else {
      // Contact form submission failed
      // You can handle errors as needed, e.g., show an error message
      console.error('Contact form submission failed');
    }
  } catch (error) {
    console.error('Error occurred:', error);
  }
};

</script>

<Navbar />

<section>

	{#if modalVisible}
		<div class="modal show">
			<img class="star sa1" src="star1-reg-mb.png" alt="star" />
			<img class="star sa2" src="star2-reg-mb.png" alt="star" />
			<img class="star sa3" src="star3-reg-mb.png" alt="star" />

			<div class="modal-content">
				<div class="image-con">
					<img src="check-modal-responsive.png" alt="check" class="check-modal" />
					<img src="man-modal-responsive.png" alt="man-dance" class="man-modal" />
				</div>
				<p class="p1">Congratulations you have successfully Registered!</p>
				<div class="wocon">
					<p class="p2">
						Yes, it was easy and you did it! check your mail box for next step
						<img src="woman-modal-responsive.png" alt="woman" />
					</p>
				</div>
				<a href="/" class="back-btn">Back</a>
			</div>
		</div>
	{/if}

	<img class="star s1" src="star1-con-mb.png" alt="star" />
	<img class="star s2" src="star2-con-mb.png" alt="star" />
	<img class="star s3" src="star3-con-mb.png" alt="star" />
	<img class="star s4" src="star4-con-mb.png" alt="star" />
	<img class="flare f1" src="flare1-con-mb.png" alt="flare1" />

	<a href="/" class="back-link mobile"><img src="back-con-mb.png" alt="back-icon" /></a>

	<div class="form-con">
		<h3 class="mobile">
			Questions or need<br />
			assistance?<br />
			Let us know about it
		</h3>

		<h3 class="desk">
			Questions or need assistance? <br />
			Let us know about it
		</h3>

		<p>Email us below to any question related to our event</p>

		<form on:submit={handleSubmit}>
			<input type="text" placeholder="Team name" bind:value={teamName} required />
			<input type="text" placeholder="Topic" bind:value={topic} required />
			<input type="email" placeholder="Email" bind:value={email} required />
			<textarea placeholder="Message" bind:value={message} required />
			<button type="submit">Submit</button>
		</form>
	</div>

	<div class="social">
		<div class="desk">
			<h2>Get in touch</h2>
			<p>Contact<br />Information</p>
			<address>
				27,Alara Street <br />
				Yaba 100012 <br />
				Lagos State
			</address>

			<p>Call Us : 07067981819</p>

			<p>
				we are open from Monday-Friday <br />
				08:00am - 05:00pm
			</p>
		</div>
		<h4>Share on</h4>
		<div class="logo">
			<a href="/" class="insta"><i class="fab fa-instagram" /></a>
			<a href="/" class="x"
				><svg class="x-logo" xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512"
					><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
					<!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
					<path
						d="M389.2 48h70.6L305.6 224.2 487 464H345L233.7 318.6 106.5 464H35.8L200.7 275.5 26.8 48H172.4L272.9 180.9 389.2 48zM364.4 421.8h39.1L151.1 88h-42L364.4 421.8z"
					/></svg
				></a
			>
			<a href="/" class="facebook"><i class="fab fa-facebook-f" /></a>
			<a href="/" class="linkedin"><i class="fab fa-linkedin-in" /></a>
		</div>
	</div>
</section>

<style>

	.modal {
		display: none;
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(21, 14, 40, 0.93);
		justify-content: center;
		align-items: center;
		z-index: 9999;
	}

	.modal.show {
		display: flex;
	}

	.modal-content {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		border-radius: 5px;
		border: 1px solid #d434fe;
		background: rgba(255, 255, 255, 0.01);
		padding: 27.08px 0;
		border-radius: 5px;
		text-align: center;
		position: relative;
	}

	.desk {
		display: none;
	}

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

	.star {
		z-index: 1;
		position: absolute;
		display: block; /* Initially visible */
		opacity: 0; /* Initially fully transparent */
		animation: fadeInOut 2s ease-in-out infinite; /* Apply the animation infinitely */
	}

	.star.s1 {
		top: 67px;
		left: 183px;
		animation-delay: 0.6s;
	}

	.star.s2 {
		top: 138px;
		right: 54px;
		animation-delay: 1.2s;
	}

	.star.s3 {
		bottom: 210px;
		right: 27px;
		animation-delay: 0s;
	}

	.star.s4 {
		bottom: 133px;
		left: 34px;
		animation-delay: 1.7s;
	}

	.flare {
		z-index: 1;
		position: absolute;
		overflow: hidden;
	}

	.f1 {
		left: 0px;
		top: 0px;
	}

	section {
		position: relative;
		display: flex;
		flex-direction: column;
		padding: 40px 40px;
		min-width: 390px;
		background: #140d27;
	}

	section > * {
		z-index: 2;
	}

	h3 {
		margin-top: 41px;
		color: #d434fe;
		font-family: Clash Display;
		font-size: 20px;
		font-style: normal;
		font-weight: 600;
		line-height: normal;
		margin-bottom: 24px;
	}

	p {
		color: #fff;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: normal;
		max-width: 239px;
		margin-bottom: 30px;
	}

	form {
		display: flex;
		flex-direction: column;
		align-items: stretch;
		justify-content: center;
		gap: 25px;
	}

	form > *:hover {
		border-color: #d434fe;
	}

	input:focus,
	textarea:focus {
		background-color: #140d27;
	}

	input {
		border-radius: 4px;
		border: 1px solid #fff;
		background: rgba(255, 255, 255, 0.03);
		box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
		height: 47px;
		padding-left: 24px;
		padding-right: 24px;
		color: #fff;
		font-size: 16px;
	}

	input::placeholder {
		color: #fff;
		font-family: Montserrat;
		font-size: 16px;
		font-style: normal;
		font-weight: 400;
		line-height: normal;
		padding: 24px;
		padding-left: 0;
	}

	textarea {
		font-size: 16px;
		color: #fff;
		border-radius: 4px;
		border: 1px solid #fff;
		background: rgba(255, 255, 255, 0.03);
		box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
		height: 180px;
		margin-bottom: 31px;
		padding: 27px 24px;
	}

	textarea::placeholder {
		color: #fff;
		font-family: Montserrat;
		font-size: 16px;
		font-style: normal;
		font-weight: 400;
		line-height: normal;
	}

	button {
		color: #fff;
		font-family: Montserrat;
		font-size: 16px;
		font-style: normal;
		font-weight: 400;
		line-height: normal;
		border-radius: 4px;
		background: linear-gradient(270deg, #903aff 0%, #d434fe 56.42%, #ff26b9 99.99%, #fe34b9 100%);
		padding: 17px 57px;
		align-self: center;
		margin-bottom: 41px;
	}

	.social {
		margin: 0 auto;
	}

	h4 {
		color: #d434fe;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: normal;
		margin: 0;
		text-align: center;
		margin-bottom: 7.04px;
	}

	.logo {
		display: flex;
		gap: 15px;
		margin-bottom: 37.13px;
	}
	.logo > * {
		color: white;
		font-size: 20px;
		fill: #ffffff;
		transition: 0.3s all ease-in-out;
		padding: 3px;
	}

	.logo > *:hover {
		transform: scale(1.2);
		color: #d434fe;
		fill: #d434fe;
	}

	@media (min-width: 880px) {

		.modal-content {
			width: 699px;
			height: 664px;
			padding: 0;
		}

		.modal-content > .p1 {
			font-size: 32px;
			max-width: 574px;
		}

		.mobile {
			display: none;
		}

		.desk {
			display: block;
		}
		section {
			flex-direction: row-reverse;
			align-items: center;
			justify-content: space-around;
			padding: 120px 160px;
			margin: 0 auto;
		}

		.form-con {
			width: 517px;
			height: 511px;
			padding: 75px 90px;
			border-radius: 12px;
			background: rgba(255, 255, 255, 0.03);
			box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
		}

		input {
			height: 47px;
		}

		textarea {
			height: 119px;
			margin: 0;
		}



		.form-con > h3 {
			margin: 0;
			margin-bottom: 10px;
		}

		.form-con > p {
			display: none;
		}

		.social {
			width: 272px;
			margin: 0;
		}

		.desk > h2 {
			color: #d434fe;

			font-size: 32px;
			font-style: normal;
			font-weight: 600;
			line-height: normal;
		}

		.desk > P,
		address {
			color: #fff;
			font-family: Montserrat;
			font-size: 16px;
			font-style: normal;
			font-weight: 400;
			line-height: 20px;
		}

		h4 {
			font-size: 16px;
			text-align: left;
		}

		.star.s1 {
			width: 21px;
			height: 25px;
			top: 100px;
			left: 205px;
			animation-delay: 0.6s;
		}

		.star.s2 {
			width: 26px;
			height: 32px;
			top: 57px;
			right: 235px;
			animation-delay: 1.2s;
		}

		.star.s3 {
			width: 30px;
			height: 36px;
			bottom: 248px;
			right: 60%;
			animation-delay: 0s;
		}

		.star.s4 {
			width: 30px;
			height: 36px;
			bottom: 113px;
			right: 129px;
			animation-delay: 1.7s;
			left: auto;
		}

		.f1 {
			width: 1037px;
			height: 948px;
			left: -150px;
			top: -200px;
		}
	}
</style>
