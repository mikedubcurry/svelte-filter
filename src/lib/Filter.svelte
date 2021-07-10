<script>
	export let items;
	export let unfiltered;
	let value = '';

	$: items = value
		? unfiltered.filter((item) => {
				return (
					item.title.toLowerCase().indexOf(value.toLowerCase()) !== -1 ||
					item.subtitle.toLowerCase().indexOf(value.toLowerCase()) !== -1 ||
					item.author.toLowerCase().indexOf(value.toLowerCase()) !== -1 ||
					item.preview.toLowerCase().indexOf(value.toLowerCase()) !== -1
				);
		  })
		: unfiltered;
</script>

<div class="filter">
	<label for="filter">Filter Posts</label>
	<input id="filter" type="text" bind:value />
</div>

<style>
	.filter {
		display: flex;
		align-items: center;
    flex-direction: column;
		margin-bottom: 4rem;
	}
  label {
    font-size: 24px;
    margin-bottom: 2rem;
    font-family: Arial, Helvetica, sans-serif;
  }
	input {
		padding: 1em;
		font-size: 18px;
	}
</style>
