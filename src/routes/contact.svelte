<style lang="scss">
$yellow: green;
	h1 {
		span {
			color: $yellow;
		}
	}
</style>

<script>
	let cats = [
		{ label: 'Address', value: 'SYSPAL, Cockshutt Lane' },
		{ label: 'Telephone', value: '07527564964' }
	];
</script>

<svelte:head>
	<title>Contact</title>
</svelte:head>

<div class="row">
	<div class="col-6">
		<img class="img-fluid" src="http://placehold.it/1000x1000" alt="">
	</div>
	<div class="col-6">
		<img class="img-fluid" src="http://placehold.it/1000x1000" alt="">
	</div>
</div>

{#each cats as cat}
	<p>{cat.label}: {cat.value}</p>
{/each}



