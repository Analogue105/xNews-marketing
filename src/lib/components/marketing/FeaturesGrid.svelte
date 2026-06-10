<section class="marketing-card p-6 sm:p-8">
	<span class="section-kicker">Feature grid</span>
	<h2 class="section-title">Everything your team needs to run returns with confidence.</h2>
	<div class="mt-6 grid gap-4 md:grid-cols-2 xl:grid-cols-3">
		{#each [
			{ title: 'Issue Reconciliation', text: 'Compare supply, sales, credits, and returns in one view.' },
			{ title: 'Mismatch Detection', text: 'Surface inventory differences before they hit billing.' },
			{ title: 'Return Batch Control', text: 'Prepare, review, and finalise batches without guesswork.' },
			{ title: 'Subagent Visibility', text: 'Track pending and finalised subagent quantities by issue.' },
			{ title: 'Operational Audit Trail', text: 'Understand movement context when numbers look wrong.' },
			{ title: 'Exception Workflow', text: 'Route anomalies into actionable issue queues.' }
		] as feature (feature.title)}
			<article class="rounded-xl border border-gray-200 bg-white p-4">
				<h3 class="text-lg font-semibold">{feature.title}</h3>
				<p class="muted mt-2 text-sm">{feature.text}</p>
			</article>
		{/each}
	</div>
</section>
