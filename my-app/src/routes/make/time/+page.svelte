<script lang="ts">
	import type { ActionData, PageServerData } from './$types';
	export let data: PageServerData;
	export let form: ActionData;
	let start_date = data.start_date;
	let end_date = data.end_date;
</script>

<main>
	<form action="/make/time" method="post">
		<label for="start_date">Start date:</label>
		<input bind:value={start_date} type="date" id="start_date" name="start_date" max={end_date} />
		<label for="end_date">End date:</label>
		<input type="date" id="end_date" name="end_date" bind:value={end_date} min={start_date} />
		<input type="submit" />
	</form>
	{#if form?.suc}
		<a href="/make/room">Next:</a>
	{/if}
</main>
