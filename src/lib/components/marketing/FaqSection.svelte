<script lang="ts">
	const items = [
		{
			q: 'Can xNews work with existing issue and barcode workflows?',
			a: 'Yes. xNews is designed around issue-level records and barcode-driven operations already common in newsagency systems.'
		},
		{
			q: 'Does it help find reconciliation gaps before returns are sent?',
			a: 'Absolutely. Reconciliation views are built to expose mismatches before finalisation so your team can act early.'
		},
		{
			q: 'Is onboarding disruptive for counter staff?',
			a: 'Most teams are operational in days, not months, with practical workflows and guided rollout support.'
		},
		{
			q: 'Do you support multi-site operators?',
			a: 'Yes. xNews can support operators managing several stores and requiring consistent controls across sites.'
		}
	];

	let openId = $state<number | null>(0);

	function toggle(idx: number) {
		openId = openId === idx ? null : idx;
	}
</script>

<section class="marketing-card p-6 sm:p-8">
	<span class="section-kicker">FAQ</span>
	<h2 class="section-title">Answers for operations teams.</h2>
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
