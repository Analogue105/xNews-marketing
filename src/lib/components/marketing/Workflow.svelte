<section class="marketing-card p-6 sm:p-8">
	<span class="section-kicker">How it works</span>
	<h2 class="section-title">Three clear steps from arrival to return.</h2>
	<div class="mt-6 grid gap-4 md:grid-cols-3">
		{#each [
			{ n: '01', title: 'Capture Arrival', text: 'Load invoice supply and issue details in seconds.' },
			{ n: '02', title: 'Reconcile Daily', text: 'Watch sales, extras, and returns shape available stock.' },
			{ n: '03', title: 'Send with Confidence', text: 'Finalise return batches with clean, auditable numbers.' }
		] as step (step.n)}
			<div class="rounded-xl border border-gray-200 bg-white p-5">
				<p class="text-xs font-bold tracking-[0.16em] text-emerald-700">{step.n}</p>
				<h3 class="mt-2 text-lg font-semibold">{step.title}</h3>
				<p class="muted mt-2 text-sm">{step.text}</p>
			</div>
		{/each}
	</div>
</section>
