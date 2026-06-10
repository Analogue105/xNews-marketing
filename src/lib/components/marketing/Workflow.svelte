<section class="marketing-card p-6 sm:p-8">
	<span class="section-kicker">How it works</span>
	<h2 class="section-title">Three operational steps teams run every week in xNews.</h2>
	<div class="mt-6 grid gap-4 md:grid-cols-3">
		{#each [
			{
				n: '01',
				title: 'Process Arrivals',
				text: 'Work magazine and newspaper arrivals, capture issue details, and stage supply for downstream workflows.'
			},
			{
				n: '02',
				title: 'Run Daily Control',
				text: 'Use lookup, returns, shortages, and subagent extras to keep issue-level quantities accurate during the week.'
			},
			{
				n: '03',
				title: 'Finalise and Report',
				text: 'Send returns, generate subagent/customer statements, and resolve flagged issues before billing windows close.'
			}
		] as step (step.n)}
			<div class="rounded-xl border border-gray-200 bg-white p-5">
				<p class="text-xs font-bold tracking-[0.16em] text-emerald-700">{step.n}</p>
				<h3 class="mt-2 text-lg font-semibold">{step.title}</h3>
				<p class="muted mt-2 text-sm">{step.text}</p>
			</div>
		{/each}
	</div>
</section>
