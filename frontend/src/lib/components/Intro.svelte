<script>
	const gag_logo = new URL('/assets/gag-logo.png', import.meta.url).href;

	const credits = `Podcast: Geschichten aus der Geschichte von Daniel Meßner und Richard Hemmer (geschichte.fm).
Wikipedia-Liste: Alle Wikipedia-Nutzer, die an der Episodenliste des Podcasts mitgearbeitet haben.
Icons: flaticon.com und kenney.nl
JavaScript-Framework: SvelteKit (kit.svelte.dev)
Netzwerkvisualisierung: vis.js (visjs.org)`;

	export let stats = {
		nodes: 0,
		edges: 0
	};
</script>

<div id="intro">
	<a
		class="-mx-5 max-h-[25%] w-[calc(100%+2.5rem)] overflow-hidden"
		href="https://www.geschichte.fm"
		target="_blank"
	>
		<img id="thumbnail" class="w-full" src={gag_logo} alt="Logo" />
	</a>
	<h1 class="my-5 text-3xl font-bold">»Flickenteppich«</h1>
	<p class="text-default">
		Diese Seite versucht den »Flickenteppich« des Podcasts&nbsp;
		<a
			href="https://www.geschichte.fm"
			target="_blank"
			class="text-primary no-underline hover:underline">»Geschichten aus der Geschichte«</a
		>
		zu visualisieren.<br />
		Die Netzwerkvisualisierung basiert auf der
		<a
			href="https://de.wikipedia.org/wiki/Geschichten_aus_der_Geschichte_(Podcast)/Episodenliste"
			target="_blank"
			class="text-primary no-underline hover:underline">&nbsp;Wikipedia-Episodenliste</a
		>
		des Podcasts und zeigt, welche Wikipedia-Artikel zu den erwähnten Themen sich gegenseitig verlinken.
		Dabei zeigen sich einige interessante Verbindungen...
	</p>
	<p
		id="stats"
		class="-mb-2 mt-10 border-y-2 border-y-light p-5 text-center text-default text-neutral-500"
	>
		<b>Themen:</b>&nbsp;&nbsp;{stats.nodes}<br />
		<b>Verbindungen:</b>&nbsp;&nbsp;{stats.edges}
	</p>
	<div class="flex flex-wrap items-center justify-center">
		<a class="small-link italic" href="https://github.com/rphle/gag-network">Quellcode</a>
		<span class="dot small-link">&middot;</span>
		<button class="small-link italic" on:click={() => alert(credits)}>Credits</button>
		<span class="dot small-link">&middot;</span>
		<a class="small-link" href="https://alpharee.de/imprint"><i>Impressum</i></a>
	</div>
</div>

<style>
	.small-link {
		display: inline-block;
		text-align: center;
		color: grey;
		cursor: pointer;
		margin-top: 20px;
		font-size: 0.7rem;
		text-decoration: none;
		display: inline-block;
	}

	.dot {
		font-weight: 900;
		margin-left: 5px;
		margin-right: 5px;
	}
</style>
