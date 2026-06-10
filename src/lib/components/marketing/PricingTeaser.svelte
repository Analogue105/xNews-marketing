<section class="marketing-card p-6 sm:p-8">
	<span class="section-kicker">Simple pricing bands</span>
	<h2 class="section-title">Choose the pace that suits your operation.</h2>
	<div class="mt-6 grid gap-4 lg:grid-cols-3">
		{#each [
			{ name: 'Launch', price: '$149', desc: 'Single-store operations and essential returns workflow.', tag: 'Best to start' },
			{ name: 'Growth', price: '$289', desc: 'Advanced reconciliation, exceptions, and performance reporting.', tag: 'Most popular' },
			{ name: 'Network', price: 'Custom', desc: 'Multi-site controls, onboarding support, and priority rollout.', tag: 'For groups' }
		] as tier (tier.name)}
			<article class="rounded-xl border border-gray-200 bg-white p-5">
				<p class="text-xs font-bold uppercase tracking-wide text-gray-500">{tier.tag}</p>
				<h3 class="mt-2 text-xl font-semibold">{tier.name}</h3>
				<p class="mt-2 text-3xl font-bold text-gray-900">{tier.price}<span class="ml-1 text-sm font-medium text-gray-500">/month</span></p>
				<p class="muted mt-2 text-sm">{tier.desc}</p>
				<button type="button" class="btn preset-outlined-surface-200-800 mt-5 w-full">Request Plan Details</button>
			</article>
		{/each}
	</div>
</section>
