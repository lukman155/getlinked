<script>
	import Navbar from '../Navbar.svelte';

	import { onMount } from 'svelte';

    const baseUrl = 'https://backend.getlinked.ai';


	let teamName = '';
	let phone = '';
	let email = '';
	let projectTopic = '';
	let categoryId = ''; // Use categoryId to store the selected category ID
	let groupSize = '';
	let terms = false;

	let modalVisible = false;

	let categories = [];

	// Function to fetch categories from the API
	async function fetchCategories() {
		try {
			const response = await fetch(`${baseUrl}/hackathon/categories-list`, {
				headers: {
					'Content-Type': 'application/json',
				},
			});
			if (response.ok) {
				const data = await response.json();
				categories = data;
			} else {
				console.error('Error fetching categories');
			}
		} catch (error) {
			console.error('Error fetching categories:', error);
		}
	}

	// Fetch categories when the component mounts
	onMount(() => {
		fetchCategories();
	});

	function handleSubmit() {
		// Prepare your form data and make the registration POST request here
		// Example:
		const formData = {
			teamName,
			phone,
			email,
			projectTopic,
			category: Number(categoryId), // Convert categoryId to a number
			groupSize,
			terms,
		};

		// Make the POST request to your registration endpoint
		fetch(`${baseUrl}/hackathon/registration`, {
			method: 'POST',
			headers: {
				'Content-Type': 'application/json',
			},
			body: JSON.stringify(formData),
		})
			.then((response) => {
				// Handle the response here, e.g., show a success message and reset the form
				if (response.ok) {
					modalVisible = true; // Show success modal
					// Reset form fields
					teamName = '';
					phone = '';
					email = '';
					projectTopic = '';
					categoryId = ''; // Clear selected category
					groupSize = '';
					terms = false;
				} else {
					// Handle the error response, e.g., show an error message
					console.error('Registration failed');
				}
			})
			.catch((error) => {
				console.error('Error:', error);
			});
	}

</script>

<Navbar />

<section class="reg-page">
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

	<img class="star s1" src="star1-reg-mb.png" alt="star" />
	<img class="star s2" src="star2-reg-mb.png" alt="star" />
	<img class="star s3" src="star3-reg-mb.png" alt="star" />
	<img class="star s4" src="star2-reg-mb.png" alt="star" />
	<img class="star s5" src="star2-reg-mb.png" alt="star" />

	<img class="flare f1" src="flare1-reg-mb.png" alt="flare1" />

	<h3 class="mobile">Register</h3>

	<div class="mansit">
		<img class="man-img" src="mansit-register-responsive.png" alt="man-icon" />
	</div>

	<div class="res-con">
		<h3 class="desk">Register</h3>

		<div class="d-line">
			<p>Be part of this movement!</p>
			<div class="line-con">
				<img src="d-line.png" alt="line" class="line" />
				<img class="icon l1" src="girl-icon-mb.png" alt="girl" />
				<img class="icon l2" src="boy-icon-mb.png" alt="boy" />
			</div>
		</div>

		<h2>CREATE YOUR ACCOUNT</h2>
		<div class="form-container {modalVisible ? 'disabled' : ''}">
			<form on:submit={handleSubmit}>
				<div class="form-con">
					<label for="teamName">Team's Name</label>
					<input type="text" id="teamName" placeholder="Team's Name" bind:value={teamName} />
				</div>

				<div class="form-con">
					<label for="phone">Phone</label>
					<input type="tel" id="phone" placeholder="Phone" bind:value={phone} />
				</div>

				<div class="form-con">
					<label for="email">Email</label>
					<input type="email" id="email" placeholder="Email" bind:value={email} />
				</div>

				<div class="form-con">
					<label for="projectTopic">Project Topic</label>
					<input
						type="text"
						id="projectTopic"
						placeholder="Project Topic"
						bind:value={projectTopic}
					/>
				</div>

				<div class="form-con">
					<label for="cat">Category</label>
					<select bind:value={categoryId} id="cat">
						<option value="" disabled hidden>Choose a category</option>
						{#each categories as cat (cat.id)}
							<option value={cat.id}>
								{#if categoryId === cat.id}
									{cat.name}
								{:else}
									{cat.name} <!-- Display category name -->
								{/if}
							</option>
						{/each}
					</select>
				</div>

					<div class="form-con">
						<label for="group">Group Size</label>

						<select bind:value={groupSize} id="group">
							<option value="" disabled hidden>Select</option>
							<option value="1">1</option>
							<option value="2">2</option>
							<option value="3">3</option>
							<option value="4">4</option>
							<option value="5">5</option>
						</select>
					</div>
				

				<h5 class="warn">Please review your registration details before submitting</h5>

				<div class="form-con term">
					<label class="custom-checkbox">
						<input type="checkbox" bind:checked={terms} />
						<span class="checkmark" />
						<p>I agree with the event terms and conditions and privacy policy.</p>
					</label>
				</div>

				<button type="submit">Submit</button>
			</form>
		</div>
	</div>
</section>

<style>
	.image-con {
		position: relative;
		margin-bottom: 46px;
	}

	.check-modal {
		position: relative;
		top: -10px;
		left: -45px;
		width: 174.617px;
		height: 174.617px;
	}

	.man-modal {
		width: 184.924px;
		height: 184.924px;
		position: absolute;
		top: 0;
		left: 35px;
	}

	.back-btn {
		margin: 0 35px 28px 35px;
		padding: 24px 126px;
		background: linear-gradient(270deg, #903aff 0%, #d434fe 56.42%, #ff26b9 99.99%, #fe34b9 100%);
		text-decoration: none;
		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 16px;
		font-style: normal;
		font-weight: 600;
		border-radius: 4px;
	}
	.wocon {
		display: flex;
		align-items: flex-end;
	}
	.p1 {
		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 16px;
		font-style: normal;
		font-weight: 600;
		line-height: normal;
		margin-bottom: 29px;
	}

	.p2 {
		color: #fff;
		text-align: center;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 500;
		line-height: normal;
		margin-bottom: 23px;
	}
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

	p > img {
		position: relative;
		width: 14px;
		height: 14px;
		top: 2px;
	}

	.form-container.disabled {
		pointer-events: none;
		opacity: 0.5;
	}

	.mansit {
		width: 195px;
		height: 155px;
		margin: 0 auto;
	}

	.mansit > img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	h5 {
		color: #ff26b9;
		font-family: Montserrat;
		font-size: 9px;
		font-style: italic;
		font-weight: 400;
		line-height: normal;
		text-align: center;
		margin: 0;
	}
	.option-form {
		display: flex;
		gap: 19px;
		width: 100%;
	}
	.option-form > * {
		flex: 1 0 auto;
	}

	.form-con {
		display: flex;
		flex-direction: column;
	}

	.custom-checkbox {
		display: flex;
	}

	label > p {
		margin-left: 10px;
		max-width: 100%;
	}

	.custom-checkbox input[type='checkbox'] {
		display: none;
	}

	/* Style the custom checkbox container */
	.custom-checkbox .checkmark {
		display: inline-block;
		width: 14px;
		height: 14px;
		background-color: #140d27; /* Background color for the checkbox */
		border-radius: 2px;
		border: 1px solid #fff; /* Rounded corners */
		margin-right: 5px; /* Spacing between checkbox and text */
	}

	/* Style the custom checkbox when it's checked */
	.custom-checkbox input[type='checkbox']:checked + .checkmark {
		background-color: #ff26b9; /* Change the background color when checked */
	}

	.form-con.term {
		flex-direction: row;
		align-items: flex-end;
		gap: 20px;
	}

	p {
		color: #fff;
		font-family: Montserrat;
		font-size: 12px;
		font-style: normal;
		font-weight: 400;
		line-height: normal;
		max-width: 239px;
		margin: 0;
	}

	h2 {
		color: #fff;
		font-family: Montserrat;
		font-size: 20px;
		font-style: normal;
		font-weight: 400;
		line-height: normal;
		margin: 0px;
		margin-bottom: 25px;
	}

	.d-line {
		display: flex;
		justify-content: center;
		align-items: center;
		position: relative;
		gap: 10px;
	}

	.line {
		position: absolute;
		bottom: 10px;
	}

	.l1 {
		margin-left: 20px;
	}

	.l2 {
		margin-left: -5px;
	}

	.icon {
		margin-bottom: 10px;
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
		top: 161px;
		right: 61px;
		animation-delay: 0.6s;
	}

	.star.s2 {
		top: 334px;
		left: 36px;
		animation-delay: 1.2s;
	}

	.star.s3 {
		bottom: 264px;
		right: 47px;
		animation-delay: 0s;
	}

	.flare {
		z-index: 0;
		position: absolute;
		overflow: hidden;
	}

	.f1 {
		left: 0px;
		top: 0px;
	}

	.reg-page {
		position: relative;
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		padding: 24px 67px;
		min-width: 390px;
		background: #140d27;
	}

	h3 {
		font-family: 'ClashDisplay-SemiBold';
		color: #d434fe;
		font-size: 15px;
		font-style: normal;
		font-weight: 700;
		line-height: normal;
		margin-bottom: 31px;
	}

	form {
		display: flex;
		flex-direction: column;
		align-items: stretch;
		justify-content: center;
		width: 100%;
		gap: 15px;
	}

	form > *:hover {
		border-color: #d434fe;
	}

	label {
		color: #fff;
		font-family: Montserrat;
		font-size: 13px;
		font-style: normal;
		font-weight: 400;
		line-height: normal;
		margin-bottom: 6px;
	}

	input:focus {
		background-color: #140d27;
	}

	input,
	select {
		color: #fff;
		border-radius: 4px;
		border: 1px solid #fff;
		background: rgba(255, 255, 255, 0.03);
		box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
		height: 39px;
		padding-left: 14px;
		padding-right: 14px;
		font-size: 13px;
	}

	option {
		font-size: 13px;
		background: #140d27;
	}

	select {
		color: #fff;
		font-family: Montserrat;
		font-size: 13px;
		font-style: normal;
		font-weight: 400;
		line-height: normal;
		padding: 0;
		padding-top: 2px;
		padding-bottom: 2px;
		padding-left: 10px;
		padding-right: 2px;
	}

	input::placeholder {
		color: rgba(255, 255, 255, 0.25);
		font-family: Montserrat;
		font-size: 13px;
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

	@media (min-width: 880px) {

		.modal-content {
			width: 699px;
height: 664px;
		}

		.modal-content > .p1 {
			font-size: 32px;
			max-width: 574px;
		}

		.p2 {
			font-size: 14px;
			max-width: 300px;
		}
		.back-btn {
			width: 274px;
		}


		form {
			display: flex;
			flex-wrap: wrap;
			justify-content: space-between;
			flex-direction: row;
		}

		form > * {
			width: calc(50% - 10px); /* Subtracting margin space */
			margin-bottom: 20px;
		}

		.warn,
		.term {
			width: 100%;
		}

		select {
			width: 100%;
		}

		select {
			widows: 100%;
		}

		button {
			width: 100%;
		}

		.warn {
			text-align: left;
		}
		.mobile {
			display: none;
		}

		.desk {
			display: block;
		}

		.mansit {
			z-index: 2;
			width: 717px;
			height: 717px;
		}
		.reg-page {
			flex-direction: row;
			align-items: center;
			justify-content: space-around;
			padding: 120px 160px;
			margin: 0 auto;
			gap: 80px;
		}

		.res-con {
			width: 740px;
			padding: 75px 90px;
			border-radius: 12px;
			background: rgba(255, 255, 255, 0.03);
			box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
		}

		.star.sa1 {
			width: 21px;
			height: 25px;
			top: 308px;
			left: 1080px;
			animation-delay: 0.6s;
		}

		.star.sa2 {
			width: 26px;
			height: 32px;
			top: 572px;
			right: 933px;
			left: auto;
			animation-delay: 1.2s;
		}

		.star.sa3 {
			width: 30px;
			height: 36px;
			bottom: 390px;
			right: 406px;
			animation-delay: 0s;
		}

		.star.s1 {
			width: 21px;
			height: 25px;
			top: 235px;
			left: 128px;
			animation-delay: 0.6s;
		}

		.star.s2 {
			width: 26px;
			height: 32px;
			top: 163px;
			right: 315px;
			left: auto;
			animation-delay: 1.2s;
		}

		.star.s3 {
			width: 30px;
			height: 36px;
			bottom: 260px;
			right: 796px;
			animation-delay: 0s;
		}

		.star.s4 {
			width: 26px;
			height: 32px;
			bottom: 106px;
		
			animation-delay: 1.7s;
			left: 139px;
		}

		.star.s5 {
			width: 10px;
			height: 12px;
			bottom: 46px;
			right: 208px;
			left: 0;
			animation-delay: 1.7s;
			left: auto;
		}

		.f1 {
			z-index: 0;
			width: 1037px;
height: 948px;
			left: -150px;
			top: -60px;
		}

		.image-con {
			transform: scale(1.2);
		}
	}
</style>
