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
{#await heroesPromise}
    Heroes are in a galaxy far far away...
{:then value}
    <!-- heroesPromise was fulfilled -->
    <ul>
        {#each heroes as hero}
            <li class="row" on:click="{() => (selectedHero = hero)}"
            class:selected={selectedHero === hero}>{hero.name}</li>
        {/each}
    </ul>
{:catch error}
    <!-- heroesPromise was rejected -->
    <div class="error">
        <p>The Sith have wiped out the heroes</p>
        <p>{error}</p>
    </div>
{/await}

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