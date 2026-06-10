<section class="marketing-card p-6 sm:p-8">
	<span class="section-kicker">Feature grid</span>
	<h2 class="section-title">Real platform capabilities used in day-to-day operations.</h2>
	<div class="mt-6 grid gap-4 md:grid-cols-2 xl:grid-cols-3">
		{#each [
			{
				title: 'Magazine Operations',
				text: 'Dashboard, lookup, shortages, arrivals, returns capture, and send returns workflows in one module.'
			},
			{
				title: 'Newspapers Workflow',
				text: 'Manage newspaper arrivals, returns, and totals with route-level operational visibility.'
			},
			{
				title: 'Subagent Management',
				text: 'Run standing orders, extras, returns, and statements with clear subagent quantity tracking.'
			},
			{
				title: 'Inventory Controls',
				text: 'Supplier invoices, suppliers, auto-order, consignment, and departments/categories management.'
			},
			{
				title: 'Customers and Accounts',
				text: 'Customer records, statements, and payments workflows that support ongoing account operations.'
			},
			{
				title: 'Labels, Issues, and xChangeIT',
				text: 'Generate labels, surface operational issues, and manage xChangeIT transfer-related processing.'
			}
		] as feature (feature.title)}
			<article class="rounded-xl border border-gray-200 bg-white p-4">
				<h3 class="text-lg font-semibold">{feature.title}</h3>
				<p class="muted mt-2 text-sm">{feature.text}</p>
			</article>
		{/each}
	</div>
</section>
