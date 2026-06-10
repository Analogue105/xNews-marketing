<section class="marketing-card p-6 sm:p-8">
	<span class="section-kicker">Final testing programme</span>
	<h2 class="section-title">xNews is currently in final testing before public release.</h2>
	<p class="muted mt-3 max-w-2xl">
		We are onboarding selected operators to validate workflows across magazines, newspapers, subagents, and reconciliation.
	</p>
	<div class="mt-6 grid gap-4 lg:grid-cols-3">
		{#each [
			{
				name: 'Pilot Intake',
				desc: 'Structured onboarding for stores ready to test operational workflows in production-like conditions.',
				tag: 'Now open'
			},
			{
				name: 'Feature Validation',
				desc: 'Collaborative testing of returns, reconciliation, statements, and issue handling prior to public release.',
				tag: 'Current phase'
			},
			{
				name: 'Release Waitlist',
				desc: 'Join the queue to receive launch timing, onboarding windows, and access details once final testing completes.',
				tag: 'Register interest'
			}
		] as tier (tier.name)}
			<article class="rounded-xl border border-gray-200 bg-white p-5">
				<p class="text-xs font-bold uppercase tracking-wide text-gray-500">{tier.tag}</p>
				<h3 class="mt-2 text-xl font-semibold">{tier.name}</h3>
				<p class="muted mt-2 text-sm">{tier.desc}</p>
				<button type="button" class="btn preset-outlined-surface-200-800 mt-5 w-full">Request Access</button>
			</article>
		{/each}
	</div>
</section>
