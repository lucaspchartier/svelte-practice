<script>
	import HeroDetail from "./HeroDetail.svelte";
	import HeroesList from "./HeroesList.svelte";

	export let name;

	let heroes = [
		{ name: "Jeff Sekinger", birthYear: 1994 },
		{ name: "Dave Portnoy", birthYear: 1977 },
		{ name: "Chamath Palihapitiya", birthYear: 1976 },
		{ name: "Cathie Wood", birthYear: 1955 }
	];
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main>

<HeroesList heroes={heroes} />
<!-- <HeroDetail {hero} /> -->

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>