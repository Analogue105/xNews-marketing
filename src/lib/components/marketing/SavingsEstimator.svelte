<script lang="ts">
	let weeklyIssues = $state(42);
	let avgMismatchCost = $state(18);
	let preventionRate = $state(0.35);

	let monthlySavings = $derived(Math.round(weeklyIssues * avgMismatchCost * preventionRate * 4.33));
	let annualSavings = $derived(monthlySavings * 12);
</script>

<section class="marketing-card p-6 sm:p-8">
	<span class="section-kicker">Interactive estimate</span>
	<h2 class="section-title">What tighter returns could save each year.</h2>
	<p class="muted mt-3 max-w-2xl">Adjust the sliders to model savings from reduced mismatches and cleaner return handling.</p>

	<div class="mt-6 grid gap-6 lg:grid-cols-[1.2fr_1fr]">
		<div class="space-y-4 rounded-xl border border-gray-200 bg-white p-5">
			<label class="block text-sm font-semibold" for="issues">Weekly issues processed: {weeklyIssues}</label>
			<input id="issues" type="range" min="10" max="140" step="1" bind:value={weeklyIssues} class="w-full" />

			<label class="block text-sm font-semibold" for="cost">Average cost per mismatch: ${avgMismatchCost}</label>
			<input id="cost" type="range" min="8" max="50" step="1" bind:value={avgMismatchCost} class="w-full" />

			<label class="block text-sm font-semibold" for="rate">Mismatch prevention rate: {Math.round(preventionRate * 100)}%</label>
			<input id="rate" type="range" min="0.1" max="0.8" step="0.01" bind:value={preventionRate} class="w-full" />
		</div>

		<div class="rounded-xl border border-emerald-100 bg-emerald-50 p-6">
			<p class="text-sm font-semibold text-emerald-800">Estimated impact</p>
			<p class="mt-2 text-3xl font-bold text-emerald-900">${monthlySavings}/month</p>
			<p class="mt-1 text-lg font-semibold text-emerald-800">${annualSavings}/year</p>
			<p class="mt-4 text-sm text-emerald-900/80">This is an indicative planning figure based on your slider settings.</p>
		</div>
	</div>
</section>
