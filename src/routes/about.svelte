<script context="module">
	import { browser, dev } from '$app/env';

	// we don't need any JS on this page, though we'll load
	// it in dev so that we get hot module replacement...
	export const hydrate = dev;

	// ...but if the client-side router is already loaded
	// (i.e. we came here from elsewhere in the app), use it
	export const router = browser;

	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<svelte:head>
	<title>NFT Minting </title>
	<meta name="description" content="About this app" />
</svelte:head>

<div class="content">
	<h1>NFT Minting </h1>

	<p>
		Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste sint asperiores minima. Esse iste ipsam ab praesentium ut fugit, nobis quod eos similique perspiciatis, quos doloribus animi impedit ipsa reprehenderit.
	</p>

	<pre>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Id molestiae odio totam quisquam neque modi adipisci culpa, unde deleniti quaerat, doloribus atque fugiat optio dolorum iure harum. Libero, possimus dolor?</pre>

	<p>
		Lorem ipsum dolor sit amet consectetur adipisicing elit. Porro, vitae! In molestiae delectus facilis perspiciatis non magni rem sequi incidunt corrupti exercitationem! Rerum maxime quisquam est eos dignissimos facilis! Nostrum.
	</p>

	<p>
		The <a href="/todos">Portfolio</a> page illustrates SvelteKit's data loading and form handling. Try using
		it with JavaScript disabled!
	</p>
</div>

<style>
	.content {
		width: 100%;
		max-width: var(--column-width);
		margin: var(--column-margin-top) auto 0 auto;
	}
</style>
