<script>
    import HeroDetail from "./HeroDetail.svelte";

    export let heroes;
    let selectedHero;

    let heroesPromise = getPeople();

    async function getPeople() {
        const response = await fetch("https://swapi.dev/api/people");
        const json = await response.json();
        return json.results;
    }
</script>

<h1>Heroes List</h1>
<ul>
    {#each heroes as hero}
        <li class="row" on:click="{() => (selectedHero = hero)}"
        class:selected={selectedHero === hero}>{hero.name}</li>
    {/each}
</ul>

{#if selectedHero}
    <HeroDetail hero={selectedHero} />
{/if}

<style>
    ul {
        list-style-type: none;
        padding: 4px;
    }
    ul > li {
        padding: 4px;
        cursor: pointer;
    }
    .selected {
        background-color: yellow;
    }
    .row {
        margin: 10px;
        box-shadow: 0 0 5px gray;
        padding: 10px 20px;
    }
    .error {
        background: rgb(255, 219, 219);
        padding: 10px 20px;
    }
</style>