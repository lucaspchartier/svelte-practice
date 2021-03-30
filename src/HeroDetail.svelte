<script>
    import { createEventDispatcher} from "svelte";
    export let hero;

    const saveHero = () => {

    };
</script>

<style>

</style>

<div>
    <div><label for="name">Name</label>
    <input type="text" name="name" bind:value={hero.name}></div>
    <div>
        <label for="birthYear">Birth Year</label>
        <input type="text" birthYear="birth year" bind:value={hero.birthYear}>
    </div>
    <button on:click="{saveHero}">Save</button>
</div>