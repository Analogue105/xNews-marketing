<script lang="ts">
	const items = [
		{
			q: 'Which parts of a newsagency workflow are covered?',
			a: 'xNews includes magazines, newspapers, subagents, customers, inventory, labels, planning, settings, and issue tracking in one platform.'
		},
		{
			q: 'Can we reconcile before finalising returns?',
			a: 'Yes. Newsagents can work through lookup, shortages, returns, send returns, and issue queues before finalising return activity.'
		},
		{
			q: 'Does xNews support subagent and customer account workflows?',
			a: 'Yes. Subagent orders, extras, returns, and statements are included, along with customer statements and payment processing workflows.'
		},
		{
			q: 'How does it handle day-to-day operational exceptions?',
			a: 'The dedicated Issues area and related workflow pages let newsagents track mismatches, assign follow-up, and resolve exceptions before billing periods close.'
		}
	];

	let openId = $state<number | null>(0);

	function toggle(idx: number) {
		openId = openId === idx ? null : idx;
	}
</script>

<section class="marketing-card p-6 sm:p-8">
	<span class="section-kicker">FAQ</span>
	<h2 class="section-title">Answers for newsagents.</h2>
	<div class="mt-6 space-y-3">
		{#each items as item, idx (item.q)}
			<article class="rounded-xl border border-gray-200 bg-white">
				<button
					type="button"
					class="flex w-full items-center justify-between px-4 py-3 text-left font-semibold"
					onclick={() => toggle(idx)}
					aria-expanded={openId === idx}
				>
					<span>{item.q}</span>
					<span>{openId === idx ? '−' : '+'}</span>
				</button>
				{#if openId === idx}
					<p class="muted px-4 pb-4 text-sm">{item.a}</p>
				{/if}
			</article>
		{/each}
	</div>
</section>
