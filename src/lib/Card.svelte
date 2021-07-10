<script>
	import { fly , fade} from 'svelte/transition';
  import {cubicIn} from 'svelte/easing'

	export let content;
</script>

<div in:fly={{duration: 200, y: 200, opacity: 0, easing: cubicIn}} out:fade={{duration: 200}}>
	<h1 class="title">{content.title}</h1>
	<p class="subtitle">{content.subtitle}</p>
	<p class="author">{content.author}</p>
	<p class="preview">{content.preview}</p>
</div>

<style>
	div {
		width: 650px;
		font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
		background-color: aqua;
		padding: 2em;
		padding-bottom: 1.5em;
		border-radius: 0 36px 0 36px;
		margin-bottom: 4rem;
	}
	.title {
		font-family: mallory;
	}
	.subtitle {
		font-size: 28px;
		/* font-weight: 400; */
		font-family: Arial, Helvetica, sans-serif;
		margin-bottom: 1em;
	}
	.author {
		padding-left: 2em;
		font-size: 20px;
		font-weight: bold;
		margin-bottom: 1.5em;
	}
	.preview {
		line-height: 2;
		font-size: 18px;
	}
</style>
