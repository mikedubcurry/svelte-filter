<script>
	import Card from './lib/Card.svelte';
	import Filter from './lib/Filter.svelte';

	const cardContent = [
		{
			id: 1,
			title: '10 Reasons Why Sveltejs is DOPE',
			subtitle: "You won't believe #9!!",
			author: 'Wes Bos',
			preview:
				'Sveltejs has been taking the world by STORM. Here are 10 reasons why I think it is the next big thing...',
		},
		{
			id: 2,
			title: 'Is this click-bait?',
			subtitle: 'Read more to find out!',
			author: 'Scott Tolinski',
			preview: "If your website looks like this, here are some things you might want to cahnge before it's too late...",
		},
		{
			id: 3,
			title: 'Why does your site suck?',
			subtitle: '16 reasons why your personal website probably sucks',
			author: 'Michael Curry',
			preview:
				"You're terrible at design... but I can help fix that! Use code deez-sign to get exclusive access to my ...",
		},
		{
			id: 4,
			title: 'Is Web Dev a Deadend Career?',
			subtitle: "What's the new hottness and how you can get in ground floor",
			author: 'Wes Bos',
			preview: 'Everything you know about the field of software development is a lie ...',
		},
		{
			id: 5,
			title: 'Svelte is a dead framework',
			subtitle: 'All the cool kids write JQuery',
			author: 'Michael Curry',
			preview: "Drop everything you're doing and check this out! Svelte and React are dead! Jquery is king!...",
		},
		{
			id: 6,
			title: "Why O(n!) is'nt that bad",
			subtitle: "And 16 other things Computer Scientists don't want  you to find out",
			author: 'Scott Tolinski',
			preview:
				"Have you ever writen an algorithm to find all permutations of a string and could'nt get fast than O(n!) running time? ...",
		},
	];
	let items = cardContent;
</script>

<main>
	<div class="cardlist">
		<Filter unfiltered={cardContent} bind:items />
		{#each items as content (content.id)}
			<Card {content} />
		{/each}
	</div>
</main>

<style>
	@font-face {
		font-family: mallory;
		src: url('/mallory.woff');
	}

	.cardlist {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-evenly;
	}

	main {
		padding: 1em;
		margin: 0 auto;
		background-color: slategrey;
		min-height: 100vh;
	}
</style>
