<script>
		import { fade, draw, fly } from 'svelte/transition';

	import FaqPage from './FaqPage.svelte';
	import Footer from './Footer.svelte';
	import HeroPage from './HeroPage.svelte';
	import IntroPage from './IntroPage.svelte';
	import JudgePage from './JudgePage.svelte';
	import Navbar from './Navbar.svelte';
	import PartnerPage from './PartnerPage.svelte';
	import PrivacyPage from './PrivacyPage.svelte';
	import PrizePage from './PrizePage.svelte';
	import RulesPage from './RulesPage.svelte';
	import TimePage from './TimePage.svelte';
</script>

<main class="container">
	<Navbar />
	<HeroPage />
	<IntroPage />
	<RulesPage />
	<JudgePage />
	<FaqPage />
	<TimePage />
	<PrizePage />
	<PartnerPage />
	<PrivacyPage />
	<Footer />
</main>

<style>
	.container {
		overflow: hidden;
		min-width: 390px;
		background: url(Purple-Lens-Flare-PNG.png) no-repeat;
		background-blend-mode: lighten;
	}

  /* CSS transitions */

  .text-transition {
    transition: opacity 0.5s ease-in-out;
  }
</style>


