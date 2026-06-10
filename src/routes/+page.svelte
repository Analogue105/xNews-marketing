<script lang="ts">
	import { onMount } from 'svelte';
	import Hero from '$lib/components/marketing/Hero.svelte';
	import SocialProof from '$lib/components/marketing/SocialProof.svelte';
	import FeaturesGrid from '$lib/components/marketing/FeaturesGrid.svelte';
	import Workflow from '$lib/components/marketing/Workflow.svelte';
	import ValueProps from '$lib/components/marketing/ValueProps.svelte';
	import SavingsEstimator from '$lib/components/marketing/SavingsEstimator.svelte';
	import PricingTeaser from '$lib/components/marketing/PricingTeaser.svelte';
	import FaqSection from '$lib/components/marketing/FaqSection.svelte';
	import FinalCta from '$lib/components/marketing/FinalCta.svelte';
	import SiteFooter from '$lib/components/marketing/SiteFooter.svelte';

	const sections = [
		{ id: 'home', label: 'Home' },
		{ id: 'features', label: 'Features' },
		{ id: 'workflow', label: 'Workflow' },
		{ id: 'pricing', label: 'Pricing' },
		{ id: 'faq', label: 'FAQ' }
	];

	let activeSection = $state('home');
	let mobileMenuOpen = $state(false);
	let revealed = $state<string[]>([]);

	const isRevealed = (id: string) => revealed.includes(id);

	function markRevealed(id: string) {
		if (revealed.includes(id)) return;
		revealed = [...revealed, id];
	}

	function scrollToSection(sectionId: string) {
		const target = document.getElementById(sectionId);
		if (!target) return;
		target.scrollIntoView({ behavior: 'smooth', block: 'start' });
		mobileMenuOpen = false;
	}

	onMount(() => {
		const revealObserver = new IntersectionObserver(
			(entries) => {
				for (const entry of entries) {
					if (!entry.isIntersecting) continue;
					const id = entry.target.getAttribute('data-reveal-id');
					if (id) markRevealed(id);
				}
			},
			{ threshold: 0.16, rootMargin: '0px 0px -10% 0px' }
		);

		const activeObserver = new IntersectionObserver(
			(entries) => {
				for (const entry of entries) {
					if (!entry.isIntersecting) continue;
					activeSection = entry.target.id || 'home';
				}
			},
			{ threshold: 0.45, rootMargin: '-30% 0px -40% 0px' }
		);

		const blocks = document.querySelectorAll<HTMLElement>('section[data-reveal-id]');
		blocks.forEach((block) => {
			revealObserver.observe(block);
			activeObserver.observe(block);
		});

		return () => {
			revealObserver.disconnect();
			activeObserver.disconnect();
		};
	});
</script>

<svelte:head>
	<title>xNews by a105.link | Smarter Newsagency Operations</title>
	<meta
		name="description"
		content="xNews by a105.link helps newsagencies run tighter returns, cleaner reconciliation, and sharper inventory decisions."
	/>
	<meta name="robots" content="index,follow" />
	<meta property="og:title" content="xNews by a105.link" />
	<meta
		property="og:description"
		content="Run faster returns, clear reconciliation, and confident inventory decisions with xNews."
	/>
	<meta property="og:type" content="website" />
	<meta name="twitter:card" content="summary_large_image" />
</svelte:head>

<div class="marketing-shell">
	<header class="top-nav">
		<a class="brand" href="#home" onclick={(event) => {
			event.preventDefault();
			scrollToSection('home');
		}}>
			<span class="brand-badge">a105.link</span>
			<span class="brand-name">xNews</span>
		</a>

		<nav class="desktop-nav" aria-label="Primary navigation">
			{#each sections as section (section.id)}
				<button
					type="button"
					class:active={activeSection === section.id}
					onclick={() => scrollToSection(section.id)}
				>
					{section.label}
				</button>
			{/each}
		</nav>

		<div class="nav-actions">
			<a class="btn preset-outlined-surface-200-800" href="#pricing" onclick={(event) => {
				event.preventDefault();
				scrollToSection('pricing');
			}}>View Pricing</a>
			<a class="btn preset-filled-primary-500" href="#final-cta" onclick={(event) => {
				event.preventDefault();
				scrollToSection('final-cta');
			}}>Book Demo</a>
		</div>

		<button type="button" class="mobile-toggle" aria-label="Toggle navigation" onclick={() => (mobileMenuOpen = !mobileMenuOpen)}>
			Menu
		</button>
	</header>

	{#if mobileMenuOpen}
		<nav class="mobile-nav" aria-label="Mobile navigation">
			{#each sections as section (section.id)}
				<button type="button" class:active={activeSection === section.id} onclick={() => scrollToSection(section.id)}>
					{section.label}
				</button>
			{/each}
		</nav>
	{/if}

	<main>
		<section id="home" data-reveal-id="home" class:is-visible={isRevealed('home')}>
			<Hero />
		</section>

		<section id="social" data-reveal-id="social" class:is-visible={isRevealed('social')}>
			<SocialProof />
		</section>

		<section id="features" data-reveal-id="features" class:is-visible={isRevealed('features')}>
			<FeaturesGrid />
		</section>

		<section id="workflow" data-reveal-id="workflow" class:is-visible={isRevealed('workflow')}>
			<Workflow />
		</section>

		<section id="value" data-reveal-id="value" class:is-visible={isRevealed('value')}>
			<ValueProps />
		</section>

		<section id="estimator" data-reveal-id="estimator" class:is-visible={isRevealed('estimator')}>
			<SavingsEstimator />
		</section>

		<section id="pricing" data-reveal-id="pricing" class:is-visible={isRevealed('pricing')}>
			<PricingTeaser />
		</section>

		<section id="faq" data-reveal-id="faq" class:is-visible={isRevealed('faq')}>
			<FaqSection />
		</section>

		<section id="final-cta" data-reveal-id="final-cta" class:is-visible={isRevealed('final-cta')}>
			<FinalCta />
		</section>
	</main>

	<SiteFooter />
</div>
